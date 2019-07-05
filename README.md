# Arc Dumaguete site

The site is made using [Jekyll](https://jekyllrb.com/docs/), which allows us to author the site using Markdown syntax, which gets compiled into HTML.

## Setting up the repositories locally

We have it setup so that the master branch contains the compiled html version, while the jekyll branch contains the jekyll source.
Then you can author in the jekyll branch, compile, and push the resulting site to the master branch. The easiest way to get this to work is to `git clone git@github.com:arc-dumaguete/arc-dumaguete.github.io.git` clone the repository, then `git checkout jekyll`. Then again, but now in side the existing clone of the jekyll branch, `git clone git@github.com:arc-dumaguete/arc-dumaguete.github.io.git ./_site`. This will clone the master branch in the `_site` directory. This directory is where jekyll will put the compiled HTML version, and that folder is ignored in `.gitignore` so won't be included in the jekyll branch. 

## Installing dependencies
Make sure you have ruby, ruby-dev (or ruby-devel in redhat/centos/fedora) and rubygem-bundler installed.
Install npm/nodejs and gulp, probably easiest through the package manager or your OS.
Run
```
bundler install
npm install
```

##Editing

Edit the files in _posts or add new files there. Make sure to look at an existing file and check the Front Matter, including the author.
New authors should be added to _authors.yml

Afterwards, don't forget to commit and push your changes.

## Building/compiling the site
Run
```
bundler exec jekyll build
```
then to publish
```
cd _site
git add *
git commit -a
git push
```

## Serving locally for testing
```
bundler exec jekyll serve
```


## Compiling styles
The styles are in assets/css. If you modify them, you need to compile them with `gulp`.
