# MkDocs.online
Seamless project documentation with [MkDocs](http://www.mkdocs.org).

## MkDocs Overview
MkDocs is a **fast**, **simple** and **downright gorgeous** static site
generator that's geared towards building project documentation. Documentation
source files are written in Markdown, and configured with a single YAML
configuration file. Start by reading the Mkdocs introductionsm, then check the User
Guide for more info.

## MkDocs.online overview
[MkDocs.online](https://mkdocs.online) is a runtime online version of MkDocs that enables seamless view MkDocs site, by providing the same functionality¹ as the original MkDocks with the difference of generating it on the client side directly from the Git reposistory.

¹There are limitation, see the section below.

### When to use MkDocs.online
Because MkDocs.online runs on the client side it enables to view the MkDocs site of every commit of the repository, without the need to deploy it.

### When not to use MkDocs.online
Because MkDocs.online runs on the client side, the loading of the page is slower then generated MkDocs site.

## Getting started
In order to use MkDocs.online, you need to provide the following values in the URL:
* site - the site that hosts the repository. Currently supports only `GitHub` and `GitLab` .
* repository owner - the user or organization that owns the repository
* repository name 
* the branch

The URL is in the following format:

`https://www.mkdocs.online/?site=<site>&owner=<owner>&repo=<repo>&branch=<branch>`

### Examples on GitHub
This site: <https://www.mkdocs.online/?site=GitHub&owner=yeger00&repo=mkdocs-online&branch=master>

MkDocs: <https://www.mkdocs.online/?site=GitHub&owner=mkdocs&repo=mkdocs&branch=master>

RedisBloom: <https://www.mkdocs.online/?site=GitHub&owner=RedisBloom&repo=RedisBloom&branch=master>

### Examples on GitLab
GitLab mkdocs example page: <https://www.mkdocs.online/?site=GitLab&owner=pages&repo=mkdocs&branch=master>

OpenCraft: <https://www.mkdocs.online/?site=GitLab&owner=opencraft&repo=documentation/public&branch=master>

## How MkDocs.online works
The code is pure JavaScript that the performs the following:
1. Fetch the docs directory from the Git repository using [Octokit](https://octokit.github.io/rest.js/v17).
1. Parse the MkDocs configuration file using [js-yaml](https://github.com/nodeca/js-yaml).
1. Generate the Page content from Markdown to HTML using [markdown-it](https://github.com/markdown-it/markdown-it) and [markdown-it-toc-and-anchor](markdown-it-toc-and-anchor).
1. Generate the final page using [nunjucks](https://mozilla.github.io/nunjucks/).

## Roadmap
The plan is to add support for the following features supported by MkDocs:
- [ ] plugins
- [ ] extensions
- [ ] search

And to add support for more Git servers:
- [ ] BitBucket

## 3rd parties License
* MkDocs: [BSD-2-Clause License](https://github.com/mkdocs/mkdocs/blob/master/LICENSE)
* Octokit: [MIT](https://github.com/octokit/rest.js/blob/master/LICENSE)
* js-yaml: [MIT](https://github.com/nodeca/js-yaml/blob/master/LICENSE)
* nunjucks: [BSD-2-Clause License](https://github.com/mozilla/nunjucks/blob/master/LICENS)
* markdown-it: [MIT](https://github.com/markdown-it/markdown-it/blob/master/LICENSE)
* markdown-it-toc-and-anchor: [MIT](https://github.com/medfreeman/markdown-it-toc-and-anchor/blob/master/LICENSE)
