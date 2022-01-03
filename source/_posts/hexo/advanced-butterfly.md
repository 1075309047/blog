---
title: Butterfly 高级技巧
tags:
  - butterfly
categories:
  - hexo
description: 標籤外掛（Tag Plugins）
date: 2022-01-02 21:58:52
updated: 2022-01-02 21:58:52
copyright_author: Jerry
copyright_author_href: https://butterfly.js.org/
copyright_url: https://butterfly.js.org/posts/4aa8abbe/
---
{% note info simple %}
標籤外掛是Hexo獨有的功能，並不是標準的Markdown格式。

以下的寫法，只適用於Butterfly主題，用在其它主題上不會有效果，甚至可能會報錯。使用前請留意。
{% endnote %}

## Note (Bootstrap Callout)

Note 標籤外掛有兩種用法

### 用法一

```html
{% note [class] [no-icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}
```

|  名稱  |  用法  |
|  ----  |  ----  |
| class | 【可選】標識，不同的標識有不同的配色<br>（ default / primary / success / info / warning / danger ） |
| no-icon | 【可選】不顯示 icon |
| style | 【可選】可以覆蓋配置中的 style<br>（simple/modern/flat/disabled） |

{% note info no-icon simple %}
info 提示塊標籤
{% endnote %}

### 用法二（自定義 icon）

```html
{% note [color] [icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}
```

|  名稱  |  用法  |
|  ----  |  ----  |
| color | 【可選】顔色<br>(default / blue / pink / red / purple / orange / green) |
| icon | 【可選】可配置自定義 icon (只支持 fontawesome 圖標, 也可以配置 no-icon ) |
| style | 【可選】可以覆蓋配置中的 style<br>（simple/modern/flat/disabled） |

{% note default no-icon modern %}
2021年快到了....
{% endnote %}

{% note blue 'fas fa-bullhorn' flat %}
2022年快到了....
{% endnote %}

## 圖庫

### Gallery圖庫

```html
<div class="gallery-group-main">
{% galleryGroup name description link img-url %}
</div>
```

<div class="gallery-group-main">
{% galleryGroup '壁紙' '收藏的一些壁紙' '/post/list/picture/wallpaper' https://i.loli.net/2019/11/10/T7Mu8Aod3egmC4Q.png %}
{% galleryGroup '插画' '好看的一些插画' '/post/list/picture/illustration' http://tvax1.sinaimg.cn/mw1024/006yt1Omgy1gxpbx4vhu9j32c01b9e81.jpg %}
</div>

### Gallery相冊

區別於舊版的Gallery相冊,新的Gallery相冊會自動根據圖片長度進行排版，書寫也更加方便，與markdown格式一樣。可根據需要插入到相應的md。

```html
{% gallery %}
markdown 圖片格式
{% endgallery %}
```

{% gallery %}
![图片描述](https://i.loli.net/2019/12/25/Fze9jchtnyJXMHN.jpg)
![图片描述](https://i.loli.net/2019/12/25/ryLVePaqkYm4TEK.jpg)
![图片描述](https://i.loli.net/2019/12/25/gEy5Zc1Ai6VuO4N.jpg)
![图片描述](https://i.loli.net/2019/12/25/d6QHbytlSYO4FBG.jpg)
![图片描述](https://i.loli.net/2019/12/25/6nepIJ1xTgufatZ.jpg)
{% endgallery %}

## tag-hide

{% note warning simple %}
請注意，tag-hide內的標簽外掛content內都不建議有h1 - h6 等標題。因為Toc會把隱藏內容標題也顯示出來，而且當滾動屏幕時，如果隱藏內容沒有顯示出來，會導致Toc的滾動出現異常。
{% endnote %}

如果你想把一些文字、內容隱藏起來，並提供按鈕讓用户點擊顯示。可以使用這個標籤外掛。

### Inline

`inline` 在文本里面添加按鈕隱藏內容，只限文字
( content不能包含英文逗號，可用`&sbquo;`)

```html
{% hideInline content,[display],[bg],[color] %}
```

* content: 文本內容
* display: 按鈕顯示的文字(可選)
* bg: 按鈕的背景顏色(可選)
* color: 按鈕文字的顏色(可選)

哪個英文字母最酷？ {% hideInline 因為西裝褲(C裝酷),查看答案,#FF7242,#fff %}

### Block

`block`獨立的block隱藏內容，可以隱藏很多內容，包括圖片，代碼塊等等
( display 不能包含英文逗號，可用`&sbquo;`)

```html
{% hideBlock [display],[bg],[color] %}
content
{% endhideBlock %}
```

查看答案
{% hideBlock 查看答案 %}
傻子，怎麼可能有答案
![alt 属性文本](./favicon.png)

```html
<p>这是隱藏的代码块</p>
```

{% endhideBlock %}

### Toggle

如果你需要展示的內容太多，可以把它隱藏在收縮框裏，需要時再把它展開
( display 不能包含英文逗號，可用`&sbquo;`)

```html
{% hideToggle [display],[bg],[color] %}
content
{% endhideToggle %}
```

{% hideToggle Butterfly安裝方法 %}
在你的博客根目錄裏

git clone -b master <https://github.com/jerryc127/hexo-theme-butterfly.git> themes/Butterfly

如果想要安裝比較新的dev分支，可以

git clone -b dev <https://github.com/jerryc127/hexo-theme-butterfly.git> themes/Butterfly

{% endhideToggle %}

## mermaid

{% note warning simple %}
mermaid標籤不允許嵌套於一些隱藏屬性的標籤外掛，例如: tag-hide內的標籤外掛和tabs標籤外掛，這會導致mermaid圖示無法正常顯示，使用時請留意。

**請不要壓縮html代碼，不然會導致mermaid顯示異常**
{% endnote %}

使用mermaid標籤可以繪製Flowchart（流程圖）、Sequence diagram（時序圖 ）、Class Diagram（類別圖）、State Diagram（狀態圖）、Gantt（甘特圖）和Pie Chart（圓形圖），具體可以查看[mermaid文檔](https://mermaid-js.github.io/mermaid/#/)

## Tabs

```html
{% tabs Unique name, [index] %}
<!-- tab [Tab caption] [@icon] -->
Any content (support inline tags too).
<!-- endtab -->
{% endtabs %}

Unique name : Unique name of tabs block tag without comma.
              Only for current url of post/page must be unique!
[index]     : 預設選擇
[Tab caption] : 当前选项卡的标题
[@icon]       : FontAwesome icon name (full-name, look like 'fas fa-font')
```

{% tabs test, -1 %} <!-- 沒有預設值 -->
<!-- tab -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab 第二個Tab -->
**tab名字為第二個Tab。**
<!-- endtab -->

<!-- tab @fab fa-apple-pay -->
**只有圖標，沒有Tab名字。**
<!-- endtab -->

<!-- tab 炸彈@fas fa-bomb -->
**名字+icon。**
<!-- endtab -->
{% endtabs %}

## Button

```html
{% btn [url],[text],[icon],[color] [style] [layout] [position] [size] %}

[url]         : 鏈接
[text]        : 按鈕文字
[icon]        : [可選] 圖標
[color]       : [可選] 按鈕背景顔色(默認style時）
                      按鈕字體和邊框顔色(outline時)
                      default/blue/pink/red/purple/orange/green
[style]       : [可選] 按鈕樣式 默認實心
                      outline/留空
[layout]      : [可選] 按鈕佈局 默認為line
                      block/留空
[position]    : [可選] 按鈕位置 前提是設置了layout為block 默認為左邊
                      center/right/留空
[size]        : [可選] 按鈕大小
                      larger/留空
```

This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,,blue %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,,outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,,blue outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}

{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,blue block center larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,blue outline block right larger %}

### more than one button in center

<div class="btn-center">
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,blue outline larger %}
</div>

## inlineImg

主題中的圖片都是默認以`塊級元素`顯示，如果你想以`內聯元素`顯示，可以使用這個標簽外掛。

```html
{% inlineImg src [height] %}

[src]      :    圖片鏈接
[height]   ：   圖片高度限制【可選】
```

你看我長得漂亮不

![alt 属性文本](https://i.loli.net/2021/03/19/2P6ivUGsdaEXSFI.png)

我覺得很漂亮 {% inlineImg "https://i.loli.net/2021/03/19/5M4jUB3ynq7ePgw.png" 150px %}

## label

高亮所需的文字

```html
{% label text [color] %}

text  文字
color 【可選】背景顏色，默認為 default
      default/blue/pink/red/purple/orange/green
```

臣亮言：{% label 先帝 %}創業未半，而{% label 中道崩殂 blue %}。今天下三分，{% label 益州疲敝 pink %}，此誠{% label 危急存亡之秋 red %}也！
