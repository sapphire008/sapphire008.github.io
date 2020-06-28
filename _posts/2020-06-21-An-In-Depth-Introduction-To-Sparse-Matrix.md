---
title: An In-Depth Introduction to Sparse Matrix
date: 2020-06-21
tags: [Python, scipy, sparse matrix, recommender system, big data, machine learnings]
category: [review]
mathjax: true
---

# Overview

Recently, as I dig deeper into recommender systems, I found that sparse matrix is the best data structure to represent the commonly used user-item matrix. In this review blog post, I will introduce `scipy.sparse` in depth, and share some lessons I have learned so far.

# Motivation to use sparse matrix

In recommender systems, we have the data on a rating of a user on a specific item. For example, on Amazon, a buyer may have a 4.5 star rating on the book Gregory Mankiw's Principles of Economics. Given there are millions or even billions of users, and hundreds of thousands of book titles on Amazon, it is not possible for every user to give a rating on every single book. Often times, we will have most of the users rating on several books, and most of the books will only have some tens to hundreds of users to rate it. If we imagine this as a matrix where the rows represent the user ids, whereas the columns represent the book id (i.e. item), then we have a very large matrix, but only with a small percentage of it filled in. Most of the entries in this matrix will be empty. This matrix, with most of the values missing or empty, will be called a **sparse matrix**. The task of a recommender system is often to predict the ratings on these missing entries in order to make recommendation to users on new items.

||**Item_1**|**Item_2**|**Item_3**|**Item_4**|...|**Item_m**|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|**User_1**|2.5|?|4.0|?|...|?|
|**User_2**|?|4.5|?|?|...|2.0|
|**User_3**|2.5|?|3.0|?|...|?|
|$\vdots$|$\vdots$|$\vdots$|$\vdots$|$\vdots$|$\vdots$|$\vdots$|
|**User_n**|4.5|?|0.0|?|...|2.0|

We can, in theory, fill all these missing values with zeros, and use `numpy.ndarray` to `pandas.DataFrame` to represent it. But every 0 we store in our memory or disk is probably a waste of memory or storage space. Also, if we fill these missing values with 0, then we wouldn't be able to distinguish cases where a user literally rate a book with 0 stars (although most rating systems probably do not allow it, perhaps also consider other types of data with potentially 0 values distinguished from missing values). Therefore, it probably makes more sense to store only the entries of the matrix where it really have some data on. Sparse matrix data structures are designed exactly for this purpose.

# Scipy's sparse matrix class

`scipy.sparse` has 7 different sparse matrix structures, each has its pros and cons in its use in practice. All 7 types are inter-convertible from each other. Some are good for slicing the matrix and do arithmetic operations on, while others are better used for constructing the data matrix from other data structures. We will analyze each one of them.

## Compressed Sparse Column Matrix `csc_matrix`

`csc_matrix` is good for column-wise slicing and fast arithmetics including `+`, `-`, `*`, `/`, power `**` and matrix multiplication `@`. `csc_matrix` is not efficient when adding a new element to the data, nor it is the best choice for constructing a new sparse matrix.

`csc_matrix` stores 3 pieces of information regarding the sparse matrix, the data itself as an array (`data`), the indices of the *rows* (`indices`), and the indirect register pointer (`indptr`) with respect to the `indices`. As an example, suppose we have the following sparse csc matrix

Then its csc representation is

```
A.data = [1, 2, 1, 2, 2, 1, 2]
A.indices = [1, 3, 2, 4, 0, 4, 4]
A.indptr = [0, 1, 2, 4, 6, 7]
```

<img src="/assets/images/csc_matrix_example.png" width="75%">

* `data` is simply a column-wise flattened version of the matrix
* `indices` is the row indices for the corresponding elements of the `data`, e.g., the first element in the data is a $1$, and it is located in the row index $1$ (second row); the second element in the data is a $2$, and the row index is $3$ (fourth row), etc...
* `indptr` is a pointer for `data` and `indices`, an array of length col + 1, with max of its element as the length of the `data` or `indices`. It is representing the range of column indices that each element in the data belongs to. For example,
  - Column $0$ have `data` and `indices` between indices `A.indptr[0] = 0` and `A.indptr[0+1] = 1`, i.e. `A.data[0:1] = 1` and `A.indices[0:1] = 1`  
  - Column $1$ have `data` and `indices` between indices `A.indptr[1] = 1` and `A.indptr[1+1] = 2`, i.e. `A.data[1:2] = 2` and `A.indices[1:2] = 3`
  - Column $2$ have `data` and `indices` between indices `A.indptr[2] = 2` and `A.indptr[2+1] = 4`, i.e. `A.data[2:4] = [1, 2]` and `A.indices[2:4] = [2, 4]`
  - Column $3$ have `data` and `indices` between indices `A.indptr[3] = 4` and `A.indptr[3+1] = 6`, i.e. `A.data[4:6] = [2, 1]` and `A.indices[4:6] = [0, 4]`
  - Column $4$ have `data` and `indices` between indices `A.indptr[4] = 6` and `A.indptr[4+1] = 7`, i.e. `A.data[6:7] = 2` and `A.indices[6:7] = 2`

## Compressed Sparse Row Matrix `csr_matrix`

`csr_matrix` is good for row-wise slicing and like `csc_matrix`, fast for arithmetic operations including `+`, `-`, `*`, `/`, power `**` and matrix multiplication `@`. `csr_matrix` is also not efficient when adding a new element to the data.

The data structure of csr matrix is similar to that of csc matrix, except that the `indices` indicates the indices of the *columns*. For the same example matrix, the csr representation is

```
A.data = [2, 1, 1, 2, 2, 1, 2]
A.indices = [3, 0, 2, 1, 2, 3, 4]
A.indptr = [0, 1, 2, 3, 4, 7]
```

where
* `data` is row-wise flattened array
* `indices` are indices of the columns
* `indptr` is a pointer for `data` and `indices`, an array of length row + 1, with max of its element as the length of the `data` or `indices`.

<img src="/assets/images/csr_matrix_example.png" width="75%">


## Block Sparse Row matrix `bsr_matrix`

`bsr_matrix` has all the advantages of `csr_matrix`. In addition, when data is dense at certain regions of the matrix, arithmetic operations can be even more efficient than `csr_matrix`. To efficiently store the sparse matrix as bsr format, it is required that the block size are all the same, and are divisible by the number of rows and columns, i.e. if block size is $(R, C)$ and matrix size is $(M, N)$, then it is required that $M % R = 0$ and $N % C = 0$.

The bsr sparse matrix representation has the following structure

* `data`: a $K \times R \times C$ matrix, where $K$ is the number of blocks, adn $R$ and $C$ are dimensions of each block.
* `indices`: length $K$ array, column indices of the blocks
* `indptr`: length $K+1$ array, pointers of block `data` and `indices`

For the following example matrix, the bsr representation is

```
A.data = [[[3, 3],  
           [3, 3]],

          [[1, 1],
           [1, 1]],

          [[2, 2],
           [2, 2]]]

A.indices = [2, 0, 1]
A.indptr = [0, 1, 2, 3]
```

<img src="/assets/images/bsr_matrix_example.png" width="75%">

## Coordinate Sparse Matrix `coo_matrix`

`coo_matrix` is the the best and fastest format for constructing a new sparse matrix using large arrays and row / column indices. Once the sparse matrix is constructed, one can easily cast it from coo to other sparse matrix formats.

A feature of `coo_matrix` format when constructing a sparse matrix is that, it allows repeated rows and columns. When converting to other sparse matrix formats such as `csc_matrix` or `csr_matrix`, the duplicated (row, col) entries will be summed together. This is especially helpful when constructing finite element matrices.

To construct a sparse matrix without summing the duplicated entries, one can use `dok_matrix`.

For the following example matrix, the `coo_matrix` structure is

```
A.data = [2, 1, 1, 2, 2, 1, 2]
A.row =  [0, 1, 2, 3, 4, 4, 4]
A.col =  [3, 0, 2, 1, 2, 3, 4]
```

<img src="/assets/images/coo_matrix_example.png" width="75%">


## Dictionary of Keys Sparse Matrix `dok_matrix`

`dok_matrix` is the best format to use when we try to update / replace the elements in a sparse matrix. It is basically a dictionary of the format `{(row, col): data, ...}`.

* `keys()`: this method will return the (row, col) tuples which indexes the data
* `values()`: this method will return the data stored

For the following matrix, the `dok_matrix`'s equivalent dict structure is

```
{(1, 0): 1,
 (3, 1): 2,
 (2, 2): 1,
 (4, 2): 2,
 (0, 3): 2,
 (4, 3): 1,
 (4, 4), 2}
```

<img src="/assets/images/dok_matrix_example.png" width="75%">


## Row-based List of List Sparse Matrix `lil_matrix`

`lil_matrix` is also a good format to construct sparse matrix, but only if the matrix does not involve a lot of data. For larger data construction, consider using `coo_matrix`. `lil_matrix` stores the following two pieces of information about the sparse matrix

* `rows`: lists of column indices for each row.
* `data`: lists of list of row elements.

For the following example matrix, when converting to lil sparse matrix, the structures are

* `rows`: \[ [3], [0], [2], [1], [2,3,4] ]
* `data`: \[ [2], [1], [1], [2], [2,1,2] ]

<img src="/assets/images/lil_matrix_example.png" width="75%">

`lil_matrix` offers a very simple and flexible interface to slice data. A key advantage of using lil format to slice the matrix is that it allows row and column indices to be broadcasted.

Suppose we have an array of row indices `rows` and column indices `cols`, to slice out a subset of the sparse matrix for every `rows` and `cols`, we can do

```
rows = rows[:, np.newaxis] # column vector
cols = cosl[np.newaxis, :] # row vector
mat_lil[rows, cols] += np.ones((rows.size, cols.size)) # add 1 on these slices
mat_lil[rows, cols] = ... # assigning these subset of slices
```

## Diagonal Storage Sparse Matrix `dia_matrix`

`dia_matrix` is the best format to use when constructing diagonal matrices, or off-diagonal matrices. It stores 2 pieces of information about the sparse matrix.

* `data`: $K x D$ matrix, where $K$ is the number of diagonal terms, and $D$ is the size fo the main diagonal.  Note that if the diagonal is at the off-diagonal (i.e. not at the main diagonal), then
  - If this is diagonal is below the main diagonal (offset < 0), then trailing zeros will be added to the array to match to the size of the main diagonal array
  - If this is diagonal is above the main diagonal (offset > 0), then leading zeros will be added to the array to match to the size of the main diagonal array
  - These zeros values can actually be any other values, but it won't be part of the matrix. In the `scipy.sparse.dia_matrix` document example, the dia matrix was constructed using 3 identical length vectors, placed at the diagonals [-1, 0, 1]. Although, when accessing the data via `A.data`, it was shown that there was no zeros filled right after the initial construction, casting first to `coo_matrix` then back to `dia_matrix` and access data with `A.data` again will show these leading and lagging zeros.
* `offsets`: array of diagonal offsets. 0 means at the main diagonal of the matrix; negative value means below the main diagonal; positive value means above the main diagonal. The array is usually sorted ascendingly (e.g. below main diagonal, main diagonal, above main diagonal)

For the following example matrix, when converting to lil sparse matrix, the structures are

```
A.data = [[2, 2, 0, 0, 0],
          [1, 1, 1, 1, 1]]
A.offsets = [-3, 0]
```

<img src="/assets/images/dia_matrix_example.png" width="75%">


## Construction and Update of 7 Sparse Matrix Formats and Inter-conversion

| **Type** | **From Dense Matrix** | **Interconversion** | **Empty Matrix** | **From Array & Row / Col Indices** | **Format-Specific Construction / Updates** |
|-|-|-|-|-|-|
| `csc_matrix` | `csc_matrix(D)` | `.tocsc()` | `csc_matrix((M,N), [dtype])` | `csc_matrix((data, (rows, cols)), [dtype])` | indices & indptr construction: `csc_matrix((data, indices, indptr), [shape=(M,N)]` |
| `csr_matrix` | `csr_matrix(D)` | `.tocsr()` | `csr_matrix((M,N), [dtype])` | `csr_matrix((data, (rows, cols)), [dtype])` | indices & indptr construction: `csr_matrix((data, indices, indptr), [shape=(M,N)]` |
| `bsr_matrix` | `bsr_matrix(D, [blocksize=(R,C)])` | `.tobsr([blocksize=(R,C))` | `bsr_matrix((M,N), [blocksize=(R,C), dtype])` | `bsr_matrix((data, (rows, cols)), [blocksize=(R,C), shape=(M,N)])` | indices & indptr construction: `bsr_matrix((data, indices, indptr), [shape=(M,N)]` |
| `coo_matrix` | `coo_matrix(D)` | `.tocoo()` | `coo_matrix((M,N), [dtype])` | `coo_matrix((data, (rows, cols)), [shape=(M,N)])` | Add new data: `mat_coo.data = np.r_[mat_coo.data, data]`, `mat_coo.row = np.r_[mat_coo.row, rows]`, `mat_coo.col = np.r_[mat_coo.col, cols]` |
| `dok_matrix` | `dok_matrix(D)` | `.todok()` | `dok_matrix((M,N), [dtype])` | N/A | row & col update: `dict.update(mat_dok, zip(zip(rows, cols), data))` |
| `lil_matrix` | `lil_matrix(D)` | `.tolil()` | `lil_matrix((M,N), [dtype])` | N/A | row & col update: `mat_lil[rows, cols] = data` |
| `dia_matrix` | `dia_matrix(D)` | `.todia()` | `dia_matrix((M,N), [dtype])` | `dia_matrix((data, offsets), shape=(M,N))` | `mat_dia.setdiag(data, offset)` |

## Comparison of all 7 sparse matrix data structures in a table

| **Type**     | **Construct New Matrix** | **Add New Element** | **Slicing**                                           | **Arithmetic Operations**                          |
|--------------|--------------------------|---------------------|-------------------------------------------------------|----------------------------------------------------|
| `csc_matrix` | slow                     | very slow           | efficient col slicing                                 | efficient                                          |
| `csr_matrix` | slow                     | very slow           | efficient row slicing                                 | efficient                                          |
| `bsr_matrix` | slow                     | very slow           | efficient row slicing                                 | Can sometimes be more efficient than  `csr_matrix` |
| `coo_matrix` | fast                     | efficient           | no native support                                     | no native support                                  |
| `dok_matrix` | efficient                | efficient           | no native support, O(1) access of individual elements | slow                                               |
| `lil_matrix` | efficient, convenient    | efficient           | flexible slicing, but slow col slicing                | slow                                               |
| `dia_matrix` | efficient                | efficient           | no native support                                     | efficient                                          |


# Sparse Matrix Broadcasting

There are many cases where want to add, subtract, or normalize over columns, rows or the entire matrix, without affecting the missing data. In this section, we are going to consider several cases of sparse matrix broadcasting.

## Scalar Broadcasting
Unlike `numpy`, simply adding a scalar on the sparse matrix with `mat_csc + 1` will give us the error

`NotImplementedError: adding a nonzero scalar to a sparse matrix is not supported`

Fortunately, the actual data of the matrix is stored in `.data` attributes as a `numpy.ndarray`. Therefore, we can simply modify the `.data` attributes,

`mat_csc.data += 1`

## Row-wise broadcasting

Suppose we have the csr sparse matrix `mat_csr` of size $M \times N$ and a row vector `array_r` of length $M$. We want to add (or subtract or element-wise multiplication or subtraction) each row of the sparse matrix by the row vector. In `numpy`, we can simply do

`mat + array_r[np.newaxis, :]`

With Sparse matrix, we again can access the `.data` attribute. We can also access the column indices of each data point via the `.indices` attribute, then the equivalent sparse matrix row-wise brodcasting is then

`mat_csr.data += np.take(array_r, mat_csr.indices)`

For other types of sparse matrices, first convert to `csr_matrix` with `tocsr()`, make the broadcasting calculation, and then convert it back to the original format.

This can be implemented as

```python
def R_plus_rv(R, rv):
    """Sparse matrix plus a row vector"""
    R = R.tocsr()
    R.data += np.take(rv, R.indices)
    return R
```

## Column-wise broadcasting

Similar for column-wise broadcasting, suppose we have csc matrix `mat_csc` of size $M \times N$ and a vector `array_c` of size $N$. If we want to broadcast the vector to all the columns of the sparse matrix, we can do

`mat_csc.data += np.take(array_c, mat_csc.indices)`

Again, for other types of sparse matrices, first convert to `csc_matrix` with `tocsc()`, make the broadcasting calculation, and then convert it back to the original format.

This can be implemented as

```python
def R_plus_cv(R, cv):
    """Sparse matrix plus a column vector"""
    R = R.tocsc()
    R.data += np.take(cv, R.indices)
    return R
```

## Sparse multiplication

In matrix factorization problems, we often need to compute a loss function after the prediction by multiplying the two factorized dense matrices. But since the loss function should only be calculated where the data is available on the large sparse matrix, it is only necessary to make the multiplication at a small subset of combinations of rows, instead of the full matrix multiplication.

Suppose we have a two dense matrices $U$ ($N \times K$) and $W$ ($M \times K$), and suppose $N$ and $M$ can be very large, but $K$ is very small. We have user-item rating sparse matrix $R$, and we are trying to use the product $\hat{R} = U.T W$ to predict $R$. Since $R$ is sparse, it is better that $\hat{R}$ is also sparse to avoid unnecessary computations.

A trick is to use `coo_matrix` to determine which combinations of rows and columns of $R$ needs to be predicted. Then slice out only the necessary rows from the two dense matrices (for necessary rows of $U$, they would be the rows of $R$; for necessary rows of $W$, they would be the columns of $R$). After selecting only the necessary rows, we can do dot products on these sliced set of row vectors. The following snippets implements this.

```python
def multiply_U_W(U, W, R):
    """Compute product of U.T and W,
    but only at the position where R is available"""
    iU, iW = R.tocoo().row, R.tocoo().col #np.nonzero(R)
    #values = np.sum(U[iU, :] * W[iW, :], axis=1)
    values = np.einsum('ij,ij->i', U[iU, :], W[iW, :])
    result = coo_matrix((values, (iU, iW))).tocsc()
    return result
```
