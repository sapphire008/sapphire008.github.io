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

## `csc_matrix`

`csc_matrix` is good for column-wise slicing and fast arithmetics including `+`, `-`, `*`, `/`, power `**` and matrix multiplication `@`. `csc_matrix` is not efficient when adding a new element to the data, nor it is the best choice for constructing a new sparse matrix.

## `csr_matrix`

`csr_matrix` is good for row-wise slicing and like `csc_matrix`, fast for arithmetic operations including `+`, `-`, `*`, `/`, power `**` and matrix multiplication `@`. `csr_matrix` is also not efficient when adding a new element to the data.

## `bsr_matrix`

`bsr_matrix` has all the advantages of `csr_matrix`. In addition, when data is dense at certain regions of the matrix, arithmetic operations can be even more efficient than `csr_matrix`.


## `coo_matrix`


## `dok_matrix`
## `lil_matrix`
## `dia_matrix`

## Construction of 7 sparse matrix and inter-conversion
| :    Easy Multiline   : |||
| :----- | :----- | :------ |
| Apple  | Banana | Orange  \
| Apple  | Banana | Orange  \
| Apple  | Banana | Orange
| Apple  | Banana | Orange  \
| Apple  | Banana | Orange  |
| Apple  | Banana | Orange  |


## Comparison of all 7 sparse matrix data structures in a table

| **Type**     | **Slicing**                                           | **Construct New Matrix** | **Add New Element** | **Arithmetic Operations**                          |
|--------------|-------------------------------------------------------|--------------------------|---------------------|----------------------------------------------------|
| `csc_matrix` | efficient col slicing                                 | slow                     | very slow           | efficient                                          |
| `csr_matrix` | efficient row slicing                                 | slow                     | very slow           | efficient                                          |
| `bsr_matrix` | efficient row slicing                                 | slow                     | very slow           | Can sometimes be more efficient than  `csr_matrix` |
| `coo_matrix` | no native support                                     | fast                     | efficient           | no native support                                  |
| `dok_matrix` | no native support, O(1) access of individual elements | efficient                | efficient           | slow                                               |
| `lil_matrix` | flexible slicing, but slow col slicing                | efficient, convenient    | efficient           | slow                                               |
| `dia_matrix` | no native support                                     | efficient                | N/A                 | efficient                                          |
