---
title: 你好，Hexo主题Butterfly！
# 相关文章 推薦的原理是根據文章tags的比重來推薦
tags:
  - butterfly
categories:
  - hexo
description: 资源访问
date: 2021-12-04 14:29:10
updated: 2021-12-24 14:29:10
# 文章顶部图
# top_img: false
# top_img: orange
top_img: https://cdn.jsdelivr.net/gh/1075309047/cdn@master/images/landscape/wallhaven-4grp97.jpg
# 文章封面
# cover: false
cover: https://cdn.jsdelivr.net/gh/1075309047/cdn@master/images/landscape/wallhaven-6qxxvq.jpg
comments: false
# 文章置顶，數值越大，置頂的優先級越大。
sticky: 1
# 顯示文章TOC
toc: true
# 文章版權
# 不需要顯示版權
# copyright: false
# 對單獨文章設置版權信息
# copyright_author: xxxx
# copyright_author_href: https://xxxxxx.com
# copyright_url: https://xxxxxx.com
# copyright_info: 此文章版權歸xxxxx所有，如有轉載，請註明來自原作者
# 代碼框是否收缩
highlight_shrink: false
# 顯示側邊欄
aside: true
# Exclude Posts/Pages
indexing: false # search
sitemap: false
---
## 访问链接

### Markdown 链接

<https://www.baidu.com>

[百度](https://www.baidu.com)

### HTML标签：超链接

<a href="https://www.baidu.com">百度</a>

`<a>` 标签的 `target` 属性规定在何处打开链接文档

* _blank：新建标签页打开，`target="_blank"`
* _self：在当前标签页打开，`target="_self"`

`<a>` 标签的 `download` 属性规定被下载的超链接目标

* 只有 Firefox 和 Chrome 支持 download 属性
* 在 `<a>` 标签中必须设置 href 属性
* 可以设置 `download` 属性的值来规定下载文件的名称，浏览器将自动检测文件扩展名并添加到文件

1. <a href="https://1075309047.github.io/blog/img/favicon.png" download="filename">点击下载</a>

2. <a href="https://1075309047.github.io/blog/img/favicon.png" download="filename">
    <img alt="favicon.png" src="https://1075309047.github.io/blog/img/favicon.png">
   </a>

## 访问文章

### 绝对路径访问文章

### 相对根路径访问文章

[根路径](/)
[博客首页](/blog)
[当前博文](/blog/post/hexo/hello-butterfly)

### 相对当前路径访问文章

md文件被渲染的实际页面
hello-butterfly.md -> hello-butterfly/index.html

[当前博文](../hello-butterfly)
[同级博文](../hello-world)
[同级博文](../hello-world/)
[同级博文](../hello-world/index)
[同级博文](../hello-world/index.html)

## 引用网络图片

### Markdown 图片

![alt 属性文本](https://cdn.jsdelivr.net/gh/1075309047/cdn@master/images/sakura/custom/avatar.jpg)

![alt 属性文本](https://cdn.jsdelivr.net/gh/1075309047/cdn@master/images/sakura/custom/avatar.jpg "头像")

### HTML标签：图像

`<img>` 标签的 `alt` 属性规定图像的替代文本
`<img>` 标签的 `height` 属性规定图像的高度
`<img>` 标签的 `width` 属性规定图像的宽度
`<img>` 标签的 `loading` 属性指定浏览器是应立即加载图像还是延迟加载图像

* eager：立即加载，`loading="eager"`
* lazy：延迟加载，`loading="lazy"`

<img alt="Smiley face" src="https://cdn.jsdelivr.net/gh/1075309047/cdn@master/images/sakura/custom/avatar.jpg" title="头像" loading="lazy" width="50%" height="10%">

## 引用本地图片

> 引用本地资源
> 将 config.yml 文件中的 post_asset_folder 选项设为 true 来打开。
> 当资源文件管理功能打开后，Hexo将会在你每一次通过 `hexo new [layout] <title>` 命令创建新文章时自动创建一个文件夹。
> 这个资源文件夹将会有与这个文章文件一样的名字。
> 将所有与你的文章有关的资源放在这个关联文件夹中之后，你可以通过相对路径来引用它们，这样你就得到了一个更简单而且方便得多的工作流。

### 绝对路径引用本地图片

### 相对根路径引用本地图片

![alt 属性文本](/blog/img/favicon.png "图标")
![alt 属性文本](/blog/post/hexo/hello-butterfly/favicon.png "图标")
![alt 属性文本](/blog/post/hexo/hello-world/favicon.png "图标")

### 相对当前路径引用本地图片

md文件被渲染的实际页面
hello-butterfly.md -> hello-butterfly/index.html

* 本博文图片

![alt 属性文本](./favicon.png)

* 同级博文图片

![alt 属性文本](../hello-world/favicon.png)

## 访问网络音频

### HTML标签：音频

#### 使用 HTML5 `<audio>` 元素

`<audio>` 标签的 `autoplay` 属性，如果出现该属性，则音频在就绪后马上播放。`<audio autoplay>`
`<audio>` 标签的 `controls` 属性，如果出现该属性，则向用户显示音频控件（比如播放/暂停按钮）。`<audio controls>`
`<audio>` 标签的 `loop` 属性，如果出现该属性，则每当音频结束时重新开始播放。`<audio loop>`

<audio controls>
  <source src="https://link.hhtjim.com/163/452971378.mp3" type="audio/mp3">
Your browser does not support the audio element.
</audio>

#### 使用超链接

如果网页包含指向媒体文件的超链接，大多数浏览器会使用“辅助应用程序”来播放文件。

<a href="https://link.hhtjim.com/163/452971378.mp3">Play Sound</a>

### 网易云音乐iframe插件

单曲的外链播放器

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=452971378&auto=0&height=66"></iframe>

## 访问本地音频

### 绝对路径访问本地音频

### 相对根路径访问本地音频

### 相对当前路径访问本地音频

## 播放网络视频

### HTML标签：视频

#### 使用 HTML5 `<video>` 标签

* `<video>` 元素支持三种视频格式：MP4、WebM、Ogg。

|  格式  |  MIME-type  |
|  :----:  |  :----:  |
| MP4 | video/mp4 |
| WebM | video/webm |
| Ogg | video/ogg |

`<video>` 标签的 `autoplay` 属性，如果出现该属性，则视频在就绪后马上播放。`<video autoplay>`
`<video>` 标签的 `controls` 属性，如果出现该属性，则向用户显示控件，比如播放按钮。`<video controls>`
`<video>` 标签的 `loop` 属性，如果出现该属性，则当媒介文件完成播放后再次开始播放。`<video loop>`
`<video>` 标签的 `muted` 属性，如果出现该属性，视频的音频输出为静音。`<video muted>`
`<video>` 标签的 `poster` 属性规定视频正在下载时显示的图像，直到用户点击播放按钮。`<video poster="URL">`
`<video>` 标签的 `height` 属性设置视频播放器的高度。
`<video>` 标签的 `width` 属性设置视频播放器的宽度。

* 注意： Internet Explorer 8 及更早IE版本不支持 `<video>` 标签。

<video controls width="95%" height="450">
  <source src="https://1075309047.github.io/blog/post/hexo/hello-butterfly/听柴璐讲哲学，回答“扎心”三连问：你是谁？从哪来？到哪去？.mp4" type="video/mp4">
your browser does not support the video tag
</video>

### 哔哩哔哩视频分享iframe代码

<iframe src="//player.bilibili.com/player.html?aid=540498305&bvid=BV1Ai4y1b7pw&cid=184163624&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" width="95%" height="450"> </iframe>

## 播放本地视频

### 绝对路径播放本地视频

### 相对根路径播放本地视频

### 相对当前路径播放本地视频
