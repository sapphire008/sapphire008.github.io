# HOW TO RELEASE

https://tianqi.name/jekyll-TeXt-theme/docs/en/quick-start

## Preparation

- diff configs (*_config.yml*, *docs/_config.yml*, *docs/_config.dev.yml*, *test/_config.yml*)
- diff data dirs (*_data*, *docs/_data*, *test/_data*)
- *assets/css/main.scss* use configurable skin
- *screenshot.jpg* is the same as *screenshots/TeXt-home.jpg*
- update *CHANGELOG.md*
- update version (*jekyll-text-theme.gemspec*, *package.json*, *_includes/scripts/variables.html*)

## Adding new posts
* Addding new posts in `_post` folder as a `.md` file

## Publishing

- run `npm run gem-build` to build gem
- run `npm run gem-push` to publish gem to rubygems.org
- run `git add . && git commit -m  "release: vx.x.x"` to make a release commit
- run `git tag vx.x.x` to add a tag
- run `git push && git push origin vx.x.x` to push
- edit release on github.com
