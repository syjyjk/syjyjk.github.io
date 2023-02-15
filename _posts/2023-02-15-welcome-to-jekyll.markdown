---
layout: post
title:  Github Blog搭建入门 (Windows操作系统)"
date:   2023-01-07 21:32:15 +0800
categories: settings
---
这篇文章记录了我作为一个新手搭建个人Blog的过程，以供在未来重装系统时参考。
对于有同样需求的初学者, 希望文章具有些借鉴意义。

本文分为两部分，第一部分介绍如何利用Jekyll生成博客模板， 第二部分介绍如何将博客模板上传到Github并在Github平台上开启个人博客站点。

## 利用Jekyll生成博客模板

Jekyll的配置主要参考自官方教程。链接地址分别是:
1. 安装Ruby Installer : [https://www.jekyll.com.cn/docs/installation/windows/](https://www.jekyll.com.cn/docs/installation/windows/)
2. 安装Jekyll与bundler, 创建Blog并启动本地服务器 : [https://www.jekyll.com.cn/docs/](https://www.jekyll.com.cn/docs/)

#### Jekyll是什么
根据Jekyll中文官网的描述，Jekyll是一个将文本转换为网页的工具。
将这些网站上传到服务器后, 其他人可以通过访问浏览这些网页(也就是访问我们的博客)。
因此Jekyll是一个很常用的博客生成工具。

#### Windows操作系统下安装Jekyll
1. 在安装Jekyll前，需要下载安装[Ruby+Devkit]。
  - 下载地址 : [https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)
  - 安装Ruby+Devkit, 尽可能在外网环境安装。
  - - 安装过程中，勾选所有选框。
  - - 弹出命令行窗口后，按照提示，选择第选项3（MSYS2 and MINGW development toolchain）。


2. 安装Jekyll与bundler gems
```
gem install jekyll bundler
```

3. 创建blog
```
jekyll new yourblogname
```

4. 启动本地Blog服务器
```
bundle exec jekyll serve
```

## 将模板上传到Github， 并在Github平台开启个人博客站点。

1. 在github上创建名为$username.github.io的repository.
2. 将Jekyll生成的一系列文件上传到repository中.


You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight julia %}
function hello_world()
  # hello world
  print("hello world")
end
hello_world()
{% endhighlight %}



Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].
 
 [jekyll-docs]: https://jekyllrb.com/docs/home
 [jekyll-gh]:   https://github.com/jekyll/jekyll
 [jekyll-talk]: https://talk.jekyllrb.com/
