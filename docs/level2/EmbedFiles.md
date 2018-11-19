# 文件嵌入

可以将文件作为 `iframe`、`video`、`audio` 或者 `code block`，如果是 Markdown 文件，甚至可以直接插入到当前文档里。

## 嵌入类型

我们可以通过 `[filename](link ':include <:type=string>')` 的方式对文件进行嵌入

目前支持

```text
iframe .html, .htm
markdown .markdown, .md
audio .mp3
video .mp4, .ogg
code other file extension
```

如果不指定 type 将会根据文件后缀设定
type

## 标签属性

如果你嵌入文件是一个 iframe、audio 或者 video，你可以给这些标签设置属性。

示例：

```md
[cinwell website](https://cinwell.com ":include :type=iframe width=100% height=400px")
```

如果嵌入的是一个代码块，可以让其自动识别或者手动设置高亮方式：

```md
[](../_media/example.html ":include :type=code text")
```
