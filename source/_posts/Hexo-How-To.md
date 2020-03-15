---
title: Hexo How-To
---
> 本文会介绍, hexo的使用
> 文章欢迎转载,但转载时请保留本段文字,并置于文章的顶部,作者:陈乐天,本文原文地址:https://theonecwd.github.io/2020/03/15/Hexo-How-To/#more
hexo是一款可以使用markdown来写博客的工具，方便部署，本文介绍如何使用hexo

## init a hexo project
```
$ hexo init
```
<!--more-->

## Create a new post

``` bash
$ hexo new "My New Post"
```

## Create tags

``` bash
$ hexo new page tags
```
## Create categories

``` bash
$ hexo new page categories
```

More info: [Writing](https://hexo.io/docs/writing.html)

## Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

## Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

## Deploy to remote sites

``` bash
$ hexo deploy
# hexo会按照_config.yaml中的配置的仓库,将public目录下的内容自动提交到git仓库
# hexo本身的工程文件,主要是md文件并不会提交到git仓库中
```

## Clean hexo project
```
$ hexo clean
```

More info: [Deployment](https://hexo.io/docs/deployment.html)

### github.io使用说明
github.io会从仓库master分支来获取内容，这些内容是通过hexo生成的静态html文件，
所以如果master分支没有这些内容，即不满足github.io的使用规则,则页面不会正常显示.
通常我们希望有个干净地方，只保存我们的源文件、图片等信息，所以需要新创建一个分支(markdown分支)
正常情况下，本地的环境只需要这个分支就够了，通过\_config.yaml中的配置来进行部署，
\_config.yaml中需要配置远程分支的位置，当执行hexo g时会使用当前分支下的内容generate
html文件hexo d时push到设置的远程分支，这个远程分支也只能是master。

平时只需要在markdown分支操作就可以了，hexo g 和 hexo d都是针对当前分支进行操作，
hexo的部署提交的commit在.deploy\_git目录中。并不会在当前分支生成commit记录(.git目录)。
markdown分支中只保存了必须的markdown文件。
为了保证markdown分支的安全，可以将该分支的remote设置成以private repo
所以在local master分支可以执行git pull操作,local master的git log都是hexo deploy生成的。


hexo只是用来生成html文件的工具,需要执行hexo init等
本地的仓库和部署的仓库可以一毛线关系都没有，github page只需要在hexo配置好远程的就可以了，
本地仓库可以push到另一仓库托管


github page的实时性不够好，push后有延迟

