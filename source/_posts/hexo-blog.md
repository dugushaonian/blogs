---
title: Hexo 搭建 blog
tags: Hexo
categories: Hexo
hidden: false
---

[Hexo](https://hexo.io/): 快速、简洁且高效的博客框架。[GitHub](https://github.com/hexojs/hexo)。

Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

这里主要记录下本人使用Hexo建站的本blog的过程。

# 一、环境准备

## 1、安装Hexo
安装Hexo前，首先要安装[Node.js](https://nodejs.org/zh-cn/)和[Git](https://git-scm.com/)（node.js和git安装见相关文档）。

然后执行如下命令安装hexo-cli
```bash
npm install hexo-cli -g
```

## 2、初始化blog
执行如下命令，hexo会初始化项目到blog目录。
```bash
hexo init blog
```

## 3、启动本地服务
```bash
cd blog
hexo server
```
然后浏览器输入：localhost:4000即可查看

# 二、Blog编辑
## 1、目录结构
创建完hexo项目后，blog中的内容如下：
![](/blogs/images/hexo-blog/hexo-blogs.png)

* source中是源文件, 文章都放到_post目录中。
* themes中是项目主题，可以去[Themes](https://hexo.io/themes/)中选择自己喜欢的主题。
* _config.yml中是项目的配置，可以在该文件中修改项目的名称等配置

# 三、部署

## 1、安装插件hexo-deployer-git
```bash
npm install hexo-deployer-git --save
```
## 2、修改_config.yml

如下：将deploy的type改成git，repo改成想要部署的github仓库地址即可，branch等其他参数选填。
```yml
deploy:
  type: git
  repo: <repository url>
  branch: [branch]
```

## 3、上传部署
上面配置完成后，只需执行如下命令即可将文件上传到对应的github仓库。
```bash
hexo d
```

> 注：当再次上传部署时，需要先执行:
> ```bash
> hexo clean
> ```
> 然后再执行：
> ```bash
> hexo d
> ```
