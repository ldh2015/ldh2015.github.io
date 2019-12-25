---
title: hexo-theme-sky使用指南
---

原文来自: https://github.com/iJinxin/hexo-theme-sky

本人仅用于学习目的，如有侵权，请及时告知，我将立即删除。

联系邮箱:  ldh2015@foxmail.com

<!-- more -->

## 功能简介

hexo-theme-sky 是一款简洁轻量的 hexo 博客主题，主要包含以下功能：

- 语言切换，目前支持中文和英文
- 文章访问统计
- 文章目录
- 评论功能，目前使用的是gitment
- 代码高亮

## 使用指南

安装 `hexo`

```
npm install hexo-cli -g
hexo init blog
```

下载 `hexo-theme-sky`主题

```
cd blog
git clone https://github.com/iJinxin/hexo-theme-sky themes/sky
```

修改博客根目录下的配置文件 `_config.yml` , 启用 `sky` 主题

```
theme: sky
```

安装依赖项

```
npm install
npm install hexo-renderer-scss --save
```

运行

```
hexo server
```

启动服务后，访问 [http://localhost:4000](http://localhost:4000/) 预览主题



本文档是对hexo-theme-sky主题的详细配置说名，只需要懂得基本git操作以及hexo命令即可轻松搭建属于自己的博客系统。

## 设置站点使用语言

主题默认使用中文，可以在 `_config_yml` 中修改 `languages` 字段进行修改

```
languages: en
```



目前支持的语言：`简体中文：zh-cn`, `英文：en`

如果你有兴趣添加其他语言在主题中可以给我发PR。

## 设置建站时间, 作者

底部默认的建站时间为今年

```
© 2019 by John Doe
```



修改 `_config` 中 `author` 字段，然后添加 `since` 字段

```
author: iJinxinsince: 2017
```



修改后的效果为

```
© 2017 - 2019 by iJinxin
```



## 添加标签页

新建标签页

```
hexo new page tags
```



编辑生成的 `tags/index.md` 文件，设置 `tags` 布局

```
layout: tags
```



在主题配置文件 `themes/_config.yml` 文件中

```
# menumenu:  Home: /  Archives: /archives  Tags: /tags
```



## 添加分类页

新建分类页

```
hexo new page categories
```



编辑生成的 `categories/index.md` 文件，设置 `categories` 布局

```
layout: categories
```



## 添加About页面

新建about页

```
hexo new page about
```



编辑生成的 `about/index.md` 文件，设置 `about` 布局

```
layout: about
```



在主题配置文件 `themes/_config.yml` 文件中

```
# menumenu:  Home: /  Archives: /archives  Tags: /tags  About: /about
```



## 设置底部社交信息

目前仅引入了github, 微博，知乎

在配置文件 `_config.yml` 添加社交账号名

```
github_username: your github usernameweibo_username:zhihu_username:
```



## 添加评论服务

主题使用了 [gitment](https://github.com/imsun/gitment)，在使用之前，需要获取client ID，和client seret。

[点击这里](https://github.com/settings/applications/new) 注册一个新的 OAuth Application。其他内容可以随意填写，但需要保证填入正确的callback URL （一般是评论页面对应的域名，如 [https://imsun.net，https://iJinxin.github.io/](https://imsun.net%2Chttps//iJinxin.github.io/) 等）

然后在配置文件 `_config.yml` 中添加评论

```
comment:  owner: your github ID  repo: 存储评论的repo  id: your client ID  secret: your client seret
```



更多关于 `gitment` 的介绍，可以查看 [作者博客](https://imsun.net/posts/gitment-introduction/)

## 发布

新完成的文章放在 `source/_posts` 目录下，在文章发布到 `github page` 前需要先安装依赖

```
npm install --save hexo-deployer-git --save
```



然后执行

```
hexo cleanhexo g -d
```



## 示例

在 `source/_post` 目录下新建 `hello.md` 文件, 内容如下

```
---
title: hello,
date: 2018-10-29 10:10:10
tags: thinking
categories: 随笔
---

这里是文章的开头部分，在设置了“阅读全文”功能后，首页只显示该部分的文字
<!-- more -->
这里是文章的剩下部分，点击“文章标题”或者“阅读全文”后才能看见。
```

