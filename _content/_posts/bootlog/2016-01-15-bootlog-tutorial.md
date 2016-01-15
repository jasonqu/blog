---
layout: index
title: Bootlog flat theme快速上手
category : bootlog
tagline: ""
tags : [bootlog, intro, beginner, tutorial]
---

欢迎阅读[bootlog](https://github.com/jasonqu/bootlog)的快速上手说明，完整的使用说明和文档请参见[bootlog in github](https://github.com/jasonqu/bootlog)。
本示例的代码都保存在[bootlogFlatDemo](https://github.com/jasonqu/bootlogFlatDemo)项目中。

## bootlog是什么

bootlog是基于sbt、twirl、pegdown、bootstrap和bootflat创建的一个静态博客生成器，目标用户是scala、java以及github使用者。

bootlog提供了两个示例，分别展示了[bootstrap主题](http://jasonqu.github.io/bootlogDemo/)和[bootflat的主题](http://jasonqu.github.io/bootlogFlatDemo/)

## 快速上手

bootlog是一个sbt插件，所以这里假设您使用sbt作为自己的常用构建工具之一。

### 几分钟完成博客创建

#### 第一步，开通github主页

* 注册[github](https://github.com/)账户
* 创建主页仓库：`{username}.github.io`
* 创建博客仓库：`blog`【记得创建它的`gh-pages`分支】
* 详细过程参见[github帮助](https://help.github.com/articles/user-organization-and-project-pages/)

#### 第二步，fork本工程

可以选择在github上直接fork[本工程](https://github.com/jasonqu/bootlogFlatDemo)，或使用命令行：

    git clone https://github.com/jasonqu/bootlogDemo blog
    cd blog
    git remote set-url origin git@github.com:USERNAME/blog.git
    git push origin master

#### 第三步，修改参数

打开`conf`目录下的`application.conf`，将其中的`rootPath`修改为自己的仓库名，如`blog`；`production_url`修改为自己的github网址——
`http://{username}.github.io`。

然后将`build.sbt`的`git.remoteRepo`修改为自己的仓库即可——`"https://github.com/{username}/{rootPath}.git"`

#### 第四步，写博客

现在万事俱备，只需要在`_content/_posts`下写自己的博客，使用`sbt ghpagesPushSite`发布网站，然后就可以在
`http://{username}.github.io/{rootPath}/`静静地欣赏自己的大作了:)

如果遇到问题，欢迎来[bootlog](https://github.com/jasonqu/bootlog/issues)提issue。
