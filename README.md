sphinx_gh-pages
===============

Sphinx と gh-pages の組み合わせ方勉強用リポジトリ。

[Welcome to sphinx_gh-pages’s documentation! — sphinx_gh-pages 1.0.0 documentation](https://mikoto2000.github.io/sphinx_gh-pages/)

gh-pages 作成手順:
------------------

Sphinx プロジェクト作成

```sh
# source と build は分割する設定にすること
# jekyll の拡張を有効にすること
$ docker-compose run --rm sphinx sphinx-quickstart
Welcome to the Sphinx 1.4.9 quickstart utility.

Please enter values for the following settings (just press Enter to
accept a default value, if one is given in brackets).

Enter the root path for documentation.
> Root path for the documentation [.]: 

You have two options for placing the build directory for Sphinx output.
Either, you use a directory "_build" within the root path, or you separate
"source" and "build" directories within the root path.
> Separate source and build directories (y/n) [n]: y

Inside the root directory, two more directories will be created; "_templates"
for custom HTML templates and "_static" for custom stylesheets and other static
files. You can enter another prefix (such as ".") to replace the underscore.
> Name prefix for templates and static dir [_]: 

The project name will occur in several places in the built documentation.
> Project name: sphinx_gh-pages
> Author name(s): mikoto2000

Sphinx has the notion of a "version" and a "release" for the
software. Each version can have multiple releases. For example, for
Python the version is something like 2.5 or 3.0, while the release is
something like 2.5.1 or 3.0a1.  If you don't need this dual structure,
just set both to the same value.
> Project version: 1.0.0
> Project release [1.0.0]: 

If the documents are to be written in a language other than English,
you can select a language here by its language code. Sphinx will then
translate text that it generates into that language.

For a list of supported codes, see
http://sphinx-doc.org/config.html#confval-language.
> Project language [en]: ja

The file name suffix for source files. Commonly, this is either ".txt"
or ".rst".  Only files with this suffix are considered documents.
> Source file suffix [.rst]: 

One document is special in that it is considered the top node of the
"contents tree", that is, it is the root of the hierarchical structure
of the documents. Normally, this is "index", but if your "index"
document is a custom template, you can also set this to another filename.
> Name of your master document (without suffix) [index]: 

Sphinx can also add configuration for epub output:
> Do you want to use the epub builder (y/n) [n]: 

Please indicate if you want to use one of the following Sphinx extensions:
> autodoc: automatically insert docstrings from modules (y/n) [n]: 
> doctest: automatically test code snippets in doctest blocks (y/n) [n]: 
> intersphinx: link between Sphinx documentation of different projects (y/n) [n]: 
> todo: write "todo" entries that can be shown or hidden on build (y/n) [n]: 
> coverage: checks for documentation coverage (y/n) [n]: 
> imgmath: include math, rendered as PNG or SVG images (y/n) [n]: 
> mathjax: include math, rendered in the browser by MathJax (y/n) [n]: 
> ifconfig: conditional inclusion of content based on config values (y/n) [n]: 
> viewcode: include links to the source code of documented Python objects (y/n) [n]: 
> githubpages: create .nojekyll file to publish the document on GitHub pages (y/n) [n]: y

A Makefile and a Windows command file can be generated for you so that you
only have to run e.g. `make html' instead of invoking sphinx-build
directly.
> Create Makefile? (y/n) [y]: 
> Create Windows command file? (y/n) [y]: 

Creating file ./source/conf.py.
Creating file ./source/index.rst.
Creating file ./Makefile.
Creating file ./make.bat.

Finished: An initial directory structure has been created.

You should now populate your master file ./source/index.rst and create other documentation
source files. Use the Makefile to build the docs, like so:
   make builder
where "builder" is one of the supported builders, e.g. html, latex or linkcheck.
$ echo "work/build" > .gitignore
$ git add .
$ git commit -m 'Initial commit.'
$ git push origin master
```

ドキュメントビルド

```sh
$ docker-compose run --rm sphinx make html
```

gh-pages ブランチ作成

```sh
$ cd work/build/html
$ git init
$ git add .
$ git commit -m 'Initial commit.'
$ git remote add origin git@github.com:mikoto2000/sphinx_gh-pages.git
$ git checkout -b gh-pages
$ git push origin gh-pages
```

License:
--------

Copyright (C) 2018 mikoto2000

This software is released under the MIT License, see LICENSE

このソフトウェアは MIT ライセンスの下で公開されています。 LICENSE を参照してください。


Author:
-------

mikoto2000 <mikoto2000@gmail.com>


