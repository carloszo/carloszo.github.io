title: 使用hexo-git-backup备份还原hexo
author: Carlos
tags:
  - 备份
categories:
  - 博客
  - ''
date: 2021-01-30 01:29:00
---
在搭建好hexo博客之后也要给自己的博客进行备份，文章丢失可是很麻烦的一件事情。好在有 hexo-git-backup 这个工具可以进行备份。
<!--more-->
## 备份
### 安装插件
如果你的Hexo版本是2.x.x（查看Hexo版本可使用命令：hexo version）在终端中使用如下命令安装：
```
$ npm install hexo-git-backup@0.0.91 --save
```
如果你的Hexo版本是3.x.x则使用如下命令安装：
```
$ npm install hexo-git-backup --save
```
### 插件配置

在博客根目录下的 _config.yml 文件中配置插件：
```
backup:
    type: git
    repository:
       github: git@github.com:xxx/xxx.git,branchName
       gitcafe: git@github.com:xxx/xxx.git,branchName
```
### 插件使用
现在就可以使用以下命令备份你的博客到GitHub了
```
$ hexo backup
```
或者
```
$ hexo b
```
## 还原
```
$ git clone -b backup https://git.coding.net/yourname/yourname.coding.me.git	# 克隆backup分支到本地，私有仓库需要输入用户名和密码
$ cd yourname.github.io			# 进入yourname.github.io文件夹
$ npm install hexo --save		# 安装hexo
$ npm install hexo-cli -g		# 安装hexo命令行模式
$ npm install	
```