# 多页面文档

如果需要创建多个页面，或者需要多级路由的网站，在 docsify 里也能很容易的实现。

目录结构：

```text
-| docs/
  -| README.md
  -| guide.md
  -| zh-cn/
    -| README.md
    -| guide.md
```

对应的页面访问地址为：

```text
docs/README.md        => http://domain.com
docs/guide.md         => http://domain.com/guide
docs/zh-cn/README.md  => http://domain.com/zh-cn/
docs/zh-cn/guide.md   => http://domain.com/zh-cn/guide
```

如果希望使用侧边栏导航到多页面，我们还需要定制侧边栏

## 定制侧边栏

默认情况下，侧边栏是通过当前文档的标题生成目录，也可以设置文档链接。通过 Markdown 文件生成。

### 配置 `loadSidebar`

_index.html_

```html
<script>
    window.$docsify = {
        loadSidebar: true
    };
</script>
```

在定制侧边栏后，侧边栏为空，此时需要创建 `_sidebar.md`

### 配置 \_sidebar.md

\__sidebar.md_

```markdown
-   [首页](zh-cn/)
-   [指南](zh-cn/guide)
```

!> 需要在文档根目录创建 .nojekyll 命名的空文件，阻止 GitHub Pages 忽略命名是下划线开头的文件。

\_sidebar.md 的加载逻辑是从每层目录下获取文件，如果当前目录不存在该文件则回退到上一级目录。例如当前路径为 `/zh-cn/more-pages` 则从 `/zh-cn/__sidebar.md` 获取文件，如果不存在则从 `/__sidebar.md` 获取。

如果想直接指向文件可以配置 `alias`

_index.html_

```html
<script>
    window.$docsify = {
        loadSidebar: true,
        alias: {
            "/.*/_sidebar.md": "/_sidebar.md"
        }
    };
</script>
```

在配置完 `loadSidebar` 后我们可能还需要显示文档目录，我们需要配置 `subMaxLevel`

### 显示目录

```html
<script>
    window.$docsify = {
        loadSidebar: true,
        subMaxLevel: 2
    };
</script>
```

当设置了 `subMaxLevel` 时，默认情况下每个标题都会自动添加到目录中。如果你想忽略特定的标题，可以给它添加 `{docsify-ignore}` 。

```markdown
# Getting Started

## Header {docsify-ignore}

该标题不会出现在侧边栏的目录中。
```

要忽略特定页面上的所有标题，你可以在页面的第一个标题上使用 `{docsify-ignore-all}` 。

```markdown
# Getting Started {docsify-ignore-all}

## Header

该标题不会出现在侧边栏的目录中。
```
