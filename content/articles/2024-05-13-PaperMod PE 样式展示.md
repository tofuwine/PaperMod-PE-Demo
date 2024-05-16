---
title: "PaperMod-PE 主题样式"
slug: 21aecad4-55c9-46ca-bb2b-2cc74427507e
description: "描述示例: 快速预览各种样式 (Hugo & PaperMod-PE 主题)"
summary: "快速预览各种样式 (Hugo & PaperMod-PE 主题)"
tags:
  - PaperMod-PE
  - Hugo
series:
  -
keywords:
  - Hugo
  - PaperMod-PE
showTop: true
weight: 1
reposted: true
repostedTitle: "PaperMod 主题个性化"
repostedAuthor: "tofuwine"
repostedLink: "https://www.tofuwine.cn/articles/site/hugo/3c96c5d2-b3f3-4a33-a2f4-0b4bb887ec97/"
draft: true
---

## 文本

| 样式     | 效果                                     |     |
|--------|----------------------------------------|-----|
| 普通文本   | This is plaintext                      |     |
| 加粗     | **This is bold text**                  |     |
| 斜体     | *This text is italicized*              |     |
| 删除     | ~~This was mistaken text~~             |     |
| 加粗嵌套斜体 | **This text is *extremely* important** |     |
| 加粗+斜体  | ***All this text is important***       |     |
| 下标     | This is a <sub>subscript</sub> text    |     |
| 上标     | This is a <sup>superscript</sup> text  |     |

部分样式通过 HTML 标签实现, 需开启配置:

```yaml { title="config.yml" }
markup:
  goldmark:
    renderer:
      unsafe: true
```

## 代码

### 行内代码

`PaperMod-PE` 是 `PaperMod` 个性化版本。

### 代码块

主要配色参考:

- light-theme: `monokailight`
- dark-theme: `github-dark`

#### 标准样式

```java
public class HelloHugo {

    public static void main(String[] args) {
        System.out.println("Hello Hugo!");
    }
}
```

#### 自定义标题

```java { title="io.github.tofuwine.main.HelloHugo.java" }
public class HelloHugo {

    public static void main(String[] args) {
        System.out.println("Hello Hugo!");
    }
}
```

#### 自定义起始行数 & 高亮指定行

```go { hl_Lines=[4,6,8], linenostart=100 }
func GetTitleFunc(style string) func(s string) string {
  switch strings.ToLower(style) {
    case "go":
      return strings.Title
    case "chicago":
      return transform.NewTitleConverter(transform.ChicagoStyle)
    default:
      return transform.NewTitleConverter(transform.APStyle)
  }
}
```

#### 折叠代码块

> Since: 2024-05-09

```java {title=HelloHugo.java fold=true}
public class HelloHugo {

    public static void main(String[] args) {
        System.out.println("Hello Hugo!");
    }
}
```

#### 更多

- ✅ 自定义语言类型显示名称 (Since 2024-05-07)
- ✅ 语法高亮使用自定义语言类型 (Since 2024-05-09)

## 引用

> 这是一段引用内容。


## ShortCode

### admonition

移植自 Hugo 的 [Loveit 主题](https://github.com/dillonzq/LoveIt)。

{{< admonition type=info title=教程参考 open=true >}}

- [如何移植HUGO Loveit主題的admonition shortcodes —— 懶懶](https://lanwp.org/18-hugo-shortcodes-admonition/)

{{< /admonition >}}

目前支持的 admonition 类型:

{{< admonition type=note title=note open=false >}}
admonition - note
{{< /admonition >}}

{{<admonition type=abstract title=abstract open=false >}}
admonition - abstract
{{< /admonition >}}

{{<admonition type=info title=info open=false >}}
admonition - info
{{< /admonition >}}

{{<admonition type=tip title=tip open=false >}}
admonition - tip
{{< /admonition >}}

{{<admonition type=success title=success open=false >}}
admonition - success
{{< /admonition >}}

{{<admonition type=question title=question open=false >}}
admonition - question
{{< /admonition >}}

{{<admonition type=warning title=warning open=false >}}
admonition - warning
{{< /admonition >}}

{{<admonition type=failure title=failure open=false >}}
admonition - failure
{{< /admonition >}}

{{<admonition type=danger title=danger open=false >}}
admonition - danger
{{< /admonition >}}

{{<admonition type=bug title=bug open=false >}}
admonition - bug
{{< /admonition >}}

{{<admonition type=example title=example open=false >}}
admonition - example
{{< /admonition >}}

{{<admonition type=quote title=quote open=false >}}
admonition - quote
{{< /admonition >}}

### hl

文本高亮。效果如下：

{{< hl >}}
This is a highlight text.
{{< /hl >}}

## Fancybox 灯箱

点击下面的图片预览效果：

![hugo logo](/images/hugo.png)

## LaTex 公式

{{<admonition type=info title=教程参考 open=true >}}
[Mathematics in Markdown —— Hugo Doc](https://gohugo.io/content-management/mathematics/)
{{< /admonition >}}

添加对 LaTex 公式/内联公式的支持。以下是效果展示：

### 块显示

$$
\begin{aligned}
KL(\hat{y} || y) &= \sum_{c=1}^{M}\hat{y}_c \log{\frac{\hat{y}_c}{y_c}} \\
JS(\hat{y} || y) &= \frac{1}{2}(KL(y||\frac{y+\hat{y}}{2}) + KL(\hat{y}||\frac{y+\hat{y}}{2}))
\end{aligned}
$$

### 内联显示

两数和的平方，等于它们的平方和加上它们的积的2倍。 即：\$(a+b)^2=a^2+2ab+b^2\$

## 目录

章节默认以 `H2` 起始，`H5` 结束。

主要改动:

- 移动至屏幕左侧显示
  {{<admonition type=info title=教程参考 open=true >}}
  [Hugo博客目录放在侧边 | PaperMod主题 —— Sulv](https://www.sulvblog.cn/posts/blog/hugo_toc_side/)
  {{< /admonition >}}
- 目录自动折叠/展开

你可以滚动界面观察左侧目录体验效果。

## 悬浮按钮

### 前往评论区 (Go to comment)

前往评论区的悬浮按钮

你可以在点击右侧对应的悬浮按钮进行体验。

### 切换主题 (Theme toggle)

切换主题按钮。主题自带切换按钮在页面顶部，在阅读文章时切换很不方便 (即使有快捷键，也对访客不是很友好)。

重新实现了一个悬浮按钮实现主题切换，同时保留 PaperMod 的切换按钮 (已禁用)。

可以点击右侧对应的悬浮按钮进行体验。

### 回到顶部 (Go to top)

回到顶部悬浮按钮, 显示进度。

{{<admonition type=info title=源码参考 open=true >}}
博主网站: 有意栽花花满枝(https://blog.hjroyal.top/)   
开源代码: https://github.com/hjroyal/hugo-papermod-flowers
{{< /admonition >}}

#### 页面跳动效果

扩展实现了当用户滚动到页面最上方/最下方后，页面轻微的跳动提示用户已到顶/底。

## 评论

📢 攻略已发布: [PaperMod 集成 Giscus 评论](https://www.tofuwine.cn/articles/site/hugo/610b75f5-54df-4203-8b25-a82065c308e5/)

## 赞赏

提供赞赏按钮，点击按钮显示微信 & 支付宝收款码，读者可扫码打赏作者。

{{<admonition type=info title=源码参考 open=true >}}
博主网站: 有意栽花花满枝(https://blog.hjroyal.top/)   
开源代码: https://github.com/hjroyal/hugo-papermod-flowers
{{< /admonition >}}

扩展实现了：

- 按钮的动态效果
- 赞赏描述 (支持国际化)
- 赞赏码/收款码弹出显示 (支持主题切换)
- 文章自定义赞赏按钮显示内容 `rewardButton`
- 文章自定义赞赏描述 `rewardSubtitle`
- 赞赏描述开关控制 `hideRewardSubtitle`

## 搜索

📢 攻略已发布: [PaperMod 添加搜索页](https://www.tofuwine.cn/articles/site/hugo/e62f6a1b-8178-442e-ac6d-6c921b3b7750/)

## 归档/时间轴

{{<admonition type=info title=教程参考 open=true >}}
[Hugo博客时间轴中文化 —— Sulv](https://www.sulvblog.cn/posts/blog/hugo_archives_chinese/)
{{< /admonition >}}

## 置顶、转载、草稿等标识

在文章页、文章列表页、归档页等界面显示置顶、转载、草稿等标识。

- 置顶：文章页、文章列表页
- 转载：文章页、文章列表页、归档页
- 草稿：归档页（文章页、文章列表页主题自带图标显示）

## Mermaid diagrams

> Since: 2024-05-07

{{<admonition type=info title=教程参考 open=true >}}
[Mermaid diagrams —— Hugo](https://gohugo.io/content-management/diagrams/#mermaid-diagrams)
{{< /admonition >}}

按官方文档添加 code block render hook。

效果参考：[Markdown 作图 —— Mermaid diagrams](https://www.tofuwine.cn/articles/note/cb59edb8-e342-487b-9c28-ffd847bb9bac/)

已知缺陷：

- 未适配 `Dark` 主题。请切换使用 `Light` 主题预览。


## 自定义页面

### 友链

{{<admonition type=info title=教程参考 open=true >}}
[Hugo 博客添加友链 —— Sulv](https://www.sulvblog.cn/posts/blog/hugo_link/)
{{</admonition>}}

### 关于

> Since: 2024-05-06

显示 `关于` 界面。

预览：[点击此处](/about)

### 最新

> Since: 2024-05-11

显示最新文章列表

预览：[点击此处](/latest)

## 文章版权声明

在文章末尾添加版权声明。

## 结尾

除了上述内容，作者还对站点很多细节进行了优化。请参阅 PaperMod-PE 源码。

