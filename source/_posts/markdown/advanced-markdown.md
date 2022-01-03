---
title: Markdown 高级技巧
tags:
  - markdown
categories:
  - post
description: Markdown 进阶
date: 2022-01-01 16:51:21
updated: 2022-01-01 16:51:21
---
## 支持的 HTML 元素

不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。

目前支持的 HTML 元素有：`<kbd> <b> <i> <em> <sup> <sub> <br>`等。

```markdown
<kbd>键盘文本</kbd>
<b>加粗文本</b>
<i>斜体文本</i>
<em>强调文本</em>
<sup>上标文本</sup>
<sub>下标文本</sub>
使用 br 标签<br>在文本中<br>换行。
<strong>重要的文本</strong>
<mark>高亮显示的文本</mark>
<u>为文本加下划线</u>
<code>计算机代码文本 print("Hello World")</code>
<img alt="Smiley face" src="http://static.runoob.com/images/runoob-logo.png" title="标题" loading="lazy" width="50%" height="10%">
```

使用 <kbd>Ctrl</kbd>+<kbd>C</kbd> 复制选中文本
<b>加粗文本</b>
<i>斜体文本</i>
<em>强调文本</em>
<sup>上标文本</sup>
<sub>下标文本</sub>
使用 br 标签<br>在文本中<br>换行。
<strong>重要的文本</strong>
<mark>高亮显示的文本</mark>
<u>为文本加下划线</u>
<code>计算机代码文本 print("Hello World")</code>
<img alt="Smiley face" src="http://static.runoob.com/images/runoob-logo.png" title="标题" loading="lazy" width="50%" height="10%">

### HTML中的字符实体

|  字符  |  转义字符  |  描述  |
|  ----  |  ----  |  ----  |
| ' ' | `&nbsp;` | 空格 |
| " | `&#34;`、`&quot;` | 双引号 |
| # | `&#35;` | 井号 |
| * | `&#42;` | 星号 |
| + | `&#43;` | 加号 |
| - | `&#45;` | 减号 |
| & | `&#38;`、`&amp;` | 与号 |
| < | `&#60;`、`&lt;` | 小于号 |
| > | `&#62;`、`&gt;` | 大于号 |
| \ | `&#92;` | 反斜杠 |
| _ | `&#95;` | 下划线 |
| \` | `&#96;` | 反引号 |

&nbsp;|空格
&#34;、&quot;|双引号
&#35;|井号
&#42;|星号
&#43;|加号
&#45;|减号
&#38;、&amp;|与号
&#60;、&lt;|小于号
&#62;、&gt;|大于号
&#92;|反斜杠
&#95;|下划线
&#96;|反引号

完整的HTML字符实体列表：[参考链接](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.freeformatter.com%2Fhtml-entities.html)

## 转义

Markdown 使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用转义字符。

Markdown 支持以下这些符号前面加上`反斜杠 \`来帮助插入普通的符号。

```markdown
\   反斜线
`   反引号
*   星号
_   下划线
{}  花括号
[]  方括号 设置超链接
()  小括号
#   井字号
+   加号
-   减号
.   英文句点
!   感叹号 用于插入图片
```

### Markdown 如何在内联代码或者代码块中使用符号反引号（`）

#### 内联代码中的反引号

单个反引号

* 双反引号包裹：``` `` ` `` ```、`` ` ``
* code标签：`` <code>`</code> ``、<code>`</code>

多个反引号

* 单反引号包裹：``` ` `` ` ```、` `` `
* 更多的反引号包裹：``` `` `<code>` `` ```
* code标签：` <code>``</code> `、<code>``</code>

内联代码中有反引号和code标签

* 合适的单引号
* 转义：<code>\`\` \`\<code>\` \`\`</code>

> 符号和内容之间必须有空格

#### 代码块中的反引号

只要代码块中的反引号数量小于三个，就能直接在代码块中使用反引号而不用担心转义问题。

但是，如果反引号的数量大于或等于三个，那么代码块的包裹就需要**比里面用更多的反引号了**。

## 公式

Markdown Preview Enhanced 使用 KaTeX 或者 MathJax 来渲染数学表达式。
