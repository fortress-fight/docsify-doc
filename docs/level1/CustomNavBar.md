# 自定义导航栏

我们可以直接在 HTML 中定义导航栏

示例：

_index.html_

```html
<body>
    <nav><a href="#/">EN</a> <a href="#/zh-cn/">中文</a></nav>
    <div id="app"></div>
</body>
```

## 配置文件

和侧边栏类似，我们可以配置 `loadNavbar`。默认加载的文件为 `_navbar.md`

_index.html_

```html
<script>
    window.$docsify = {
        loadNavbar: true
    };´
</script>
```

然后设置 `_navbar.md`，例如：

\__navbar.md_

```markdown
-   [首页](/)
-   [多页面](/docs/MorePages)
```

如果导航内容较多，可以写成嵌套的列表这种列表会被渲染成为下拉列表的形式

\__navbar.md_

```markedown
* 基础
  * [快速开始](zh-cn/quickstart.md)
  * [多页文档](zh-cn/more-pages.md)
  * [定制导航栏](zh-cn/custom-navbar.md)
  * [封面](zh-cn/cover.md)

* 配置
  * [配置项](zh-cn/configuration.md)
  * [主题](zh-cn/themes.md)
  * [使用插件](zh-cn/plugins.md)
  * [Markdown 配置](zh-cn/markdown.md)
  * [代码高亮](zh-cn/language-highlight.md)
```

!>一份文档只会在根目录下加载封面，其他页面或者二级目录下都不会加载。
