---
title: Hexo HowTo
---

## Quick Start

### Create a new post

``` bash
$ hexo new "My New Post"
```

### Create tags

``` bash
$ hexo new page tags
```
### Create categories

``` bash
$ hexo new page categories
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` bash
$ hexo deploy
# hexo会按照_config.yaml中的配置的仓库,将public目录下的内容自动提交到git仓库
# hexo本身的工程文件,主要是md文件并不会提交到git仓库中
```


### Clean hexo project
```
$ hexo clean
```

More info: [Deployment](https://hexo.io/docs/deployment.html)

### github.io使用说明
github.io会从仓库默认分支来获取内容，主要是通过hexo生成并部署的html文件，
所以如果默认分支没有这些内容，即不满足github.io的使用规则,则页面不会正常显示.
通常我们希望有个干净地方，只保存我们的源文件、图片等信息，所以需要新创建一个分支，
正常情况下，本地的环境只需要这个分支就够了，通过\_config.yaml中的配置来进行部署，新generate的
html内容push到另外一个分支，该分支需要在github仓库上面设置为默认分支

github会默认从master分支来获取内容来显示页面，所以在\_config.yaml 需要配置成远程的master
但是需要一个分支来显示markdown文档，所以需要将本地master 推送到远程的markdown分支，以后若是要变更，需要
markdown分支(我的远程markdown分支被我写成了blog分支)

上面说的好像不对，貌似没有办法处理这个情况
因为要把master 与 origin master同步，origin master会显示静态页面


