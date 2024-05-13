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
draft: false
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

### hl

文本高亮。效果如下：

{{< hl >}}
This is a highlight text.
{{< /hl >}}

## Fancybox 灯箱

点击下面的图片预览效果：

![hugo logo](/images/hugo.png)

