# 文档助手

docsify 扩展了一些 Markdown 语法，可以让文档更易读。

## 引用相关

### 强调内容

适合显示重要的提示信息，语法为 !> 内容。

```md
!> 一段重要的内容，可以和其他 **Markdown** 语法混用。
```

渲染后：

!> 一段重要的内容，可以和其他 **Markdown** 语法混用。

### 普通提示

普通的提示信息，比如写 TODO 或者参考内容等。

```md
?> _TODO_ 完善示例
```

渲染后：

?> _TODO_ 完善示例

## Link 相关

### 忽略编译链接

有时候我们会把其他一些相对路径放到链接上，你必须告诉 docsify 你不需要编译这个链接。 例如：

```md
[link](/demo/)
```

它将被编译为 `<a href="/#/demo/">link</a>` 并将加载 `/demo/README.md`. 可能你想跳转到 `/demo/index.html`。

可以使用：

```md
[link](/demo/ ":ignore <title>")
```

### 设置链接的 target

```md
[link](/demo ":target=_blank")
[link](/demo2 ":target=_self")
```

## 任务列表

```md
-   [ ] foo
-   bar
-   [x] baz
-   [] bam <~ not working
    -   [ ] bim
    -   [ ] lim
```

渲染后：

-   [ ] foo
-   bar
-   [x] baz
-   [] bam <~ not working
    -   [ ] bim
    -   [ ] lim

## image resizing

```md
![logo](https://docsify.js.org/_media/icon.svg ":size=50x100")
![logo](https://docsify.js.org/_media/icon.svg ":size=100")
```

## 设置标题的 id 属性

```md
### 你好，世界！ :id=hello-world
```
