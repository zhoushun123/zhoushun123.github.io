---
layout: post
title:  "第一篇笔记"
date:   2018-12-29 14:05:44 +0800
categories: jekyll
tags: jekyll Github Gitalk
---

* content
{:toc}

一直以来就想在Github上搭建一个blog，为什么？因为感觉比较Geek。拖拖拉拉，东看西看，终于下定决心动手了，基本上就是copy&paste，没什么技术含量，只是前面花了不少时候找合适的jekyll主题。第一篇笔记不名俗地来了个`Hello Blog`。





## 过程

一开始在[jekyll](https://jekyllrb.com)和[hexo](https://hexo.io)之前犹豫了很久，发现hexo搭的都太花哨了，而且Github天生支持jekyll，又刚才发现了几个不错的jekyll主题，完成度都比较高，不需要再费太多功夫设置。我的要求就是主题简单，颜色少，以暗色为主，不要动画，不要背景图片，能让人精力集中到内容上，但也不能太简陋。后来终于找到满意的：

主页：
![index]({{ "/assets/images4post/2018-12-29-hello-blog/index.jpg" | absolute_url }})

文章页：
![post]({{ "/assets/images4post/2018-12-29-hello-blog/post.jpg" | absolute_url }})

色调、布局都很对口味，就这个了。仔细研究了一下，评论系统可能有问题，不是关了就是墙了，后来发现[Gitalk](https://github.com/gitalk/gitalk/)，和Github简直是绝配，用起来也简单，就它了。

### 第一步：fork

把[Gaohaoyang](https://github.com/Gaohaoyang/gaohaoyang.github.io)这个repo fork下来，git clone到本地。

### 第二步：改配置

repo里有说明怎么改，主要改`_config.yml`，把里面的个人信息改成自己的，再加上`Gitalk`的信息（`_includes/comments.html`同时要改），然后是about页（`page/4about.md`），再把`_post`里的内容清空，就开始写本篇笔记了。图片不打算用外面的图床了，直接扔到`assets`下面本地引用比较稳，当然引用方式研究了一下。

### 第三步：踩坑

高高兴兴地`jekyll s`，期待中的页面并没有出现，还是那个清空的Blog……控制台也没任何报错，就是显示不出来。试着还原了一个清空的post，**可以显示。WTF。** 系统还认人的吗，不科学。后来各种折腾，改文件名，改文件内容，直接从原来的post复制粘贴，最终发现可能是文件头中的date的问题，我写的时间是一会儿之前，改到昨天，可以显示了。这也没道理。后来想到这可能是时区的问题，用`jekyll 时区`关键词谷（百）歌（度）了一下，果然。后来仔细看了一下原repo里的教程，里面其实写了，但不是我眼瞎，这也太不明显了，不踩坑谁能注意到。

![]({{ "/assets/images4post/2018-12-29-hello-blog/timezone.jpg" | absolute_url }})

最后只有评论系统和Baidu/Google分析没验证了，这个本地验证不了，得push到Github才行。那本地修改就到此为止了，push吧，祝我好运。