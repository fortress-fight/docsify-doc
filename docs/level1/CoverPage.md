# 封面

通过设置 `coverpage` 参数，可以开启渲染封面的功能

## 基本使用

封面的生成同样是从 markdown 文件渲染来的。开启渲染封面功能后在文档根目录创建 \_coverpage.md 文件。渲染效果如本文档。

_index.html_

```html
<script>
    window.$docsify = {
        coverpage: true
    };
</script>
```

如果希望封面作为首页存在，可以通过设置 `onlyCover: true` 来实现

```html
<script>
    window.$docsify = {
        coverpage: true,
        onlyCover: true
    };
</script>
```

\__coverpage.md_

```markdown
![logo](_media/icon.svg)

# docsify

> A magical documentation site generator.

-   Simple and lightweight (~12kb gzipped)
-   Multiple themes
-   Not build static html files

[GitHub](https://github.com/docsifyjs/docsify/)
[Get Started](#quick-start)
```

![coverpage](http://resources.ffstone.top/resource/image/coverpage)

## 自定义背景

目前的背景是随机生成的渐变色，我们自定义背景色或者背景图。在文档末尾用添加图片的 Markdown 语法设置背景。

\__coverpage.md_

```markdown
![logo](_media/icon.svg)

# docsify

> A magical documentation site generator.

-   Simple and lightweight (~12kb gzipped)
-   Multiple themes
-   Not build static html files

[GitHub](https://github.com/docsifyjs/docsify/)
[Get Started](#quick-start)

<!-- 背景图片 -->

![](_media/bg.png)

<!-- 背景色 -->

![color](#f0f0f0)
```

## 多封面设置

如果你的网站需要多个封面可以设置

例如：

```js
coverpage: ["/", "/zh-cn/"];
```

然后在 `"/"` 和 "/zh-cn/" 下各创建一个 `_coverpage.md` 文件。或者指明具体的文件名：

```js
coverpage: {
    '/': 'cover.md',
    '/zh-cn/': 'cover.md'
}
```
