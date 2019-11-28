---
layout: default
title: Getting Started
nav_order: 2
---

# Getting Started
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


If this is the first time you contribute to OpenSSL, there might be a lot of things which are new to you.



## Getting started with GitHub

The GitHub Help site has detailed information about [Getting started with GitHub][get-started], which we don't want to replicate here.

If you never used Git version control system before, take a look at the excellent [Pro Git][pro-git] book by Scott Chacon (a co-founder of GitHub) and Ben Straub. It is free and you can read it online or download an offline copy. The book serves both as a tutorial for beginners and a valuable reference for the experienced user. It also contains a chapter dedicated to the GitHub workflow.

## Setting up the Repositories

You need two repositories, a public fork on GitHub, and a local working copy.


| Repository                | Name     |  URL/Location                            |
|:--------------------------|:---------|:-----------------------------------------|
| Main OpenSSL repository   | openssl  |  git://git.openssl.org/openssl.git       |
| Official GitHub mirror    | github   |  https://github.com/openssl/openssl.git  |
| Your GitHub fork          | origin   |  https://github.com/yourname/openssl.git |
| Your local working copy   |          |  ~/src/openssl                           |

The main OpenSSL repository is mentioned here only for completeness. As a normal contributor, you will not need to add it as a remote repository. Only for committers this repository will be of importance.

### Fork the OpenSSL GitHub Repository

Follow the [GitHub instructions](https://help.github.com/en/github/getting-started-with-github/fork-a-repo) to create a fork of the OpenSSL GitHub mirror:

```
    https://github.com/openssl/openssl.git -> https://github.com/yourname/openssl.git
```

### Clone your public fork into a local repository

For all examples, the local repository will be located at ~/src/openssl. Of course you can choose a different location if you prefer.

```
~$ cd ~/src
~/src$ git clone https://github.com/yourname/openssl.git
~/src$ cd openssl
```

The git remote command now shows your clone as the origin:

```
~/src/openssl$ git remote -v
origin	https://github.com/yourname/openssl.git (fetch)
origin	https://github.com/yourname/openssl.git (push)
```

From now on, it will be assumed that all shell commands are issued in the ~/src/openssl directory and the ~/src/openssl$ shell prompt will be shortened to a simple $.


### Add the GitHub mirror as second remote repository

```
$ git remote add openssl https://github.com/openssl/openssl.git
```

```
$ git remote -v
origin	https://github.com/yourname/openssl.git (fetch)
origin	https://github.com/yourname/openssl.git (push)
openssl	https://github.com/openssl/openssl.git (fetch)
openssl	https://github.com/openssl/openssl.git (push)
```


```
$ git branch --set-upstream-to=openssl/master
Branch 'master' set up to track remote branch 'master' from 'openssl'.
```

To be continued...

[pro-git]: https://git-scm.com/book/en/v2
[get-started]: https://help.github.com/en/github/getting-started-with-github
