# 配置项

`window.$docsify` 里的配置项

## 基础

### el

docsify 初始化的挂载元素，可以是一个 CSS 选择器，默认为 #app 如果不存在就直接绑定在 body 上。

### repo

配置仓库地址或者 username/repo 的字符串，会在页面右上角渲染一个 GitHub Corner 挂件。

### maxLevel

默认情况下会抓取文档中所有标题渲染成目录，可配置最大支持渲染的标题层级。

### loadNavbar

设置为 true 后会加载 \_navbar.md 文件，也可以自定义加载的文件名。

### loadSidebar

设置为 true 后会加载 \_sidebar.md 文件，也可以自定义加载的文件名。

### autoHeader

如果设置了 `loadSidebar`, 那么我们可以利用 `autoHeader` 自动为页面添加标题

### subMaxLevel

自定义侧边栏后默认不会再生成目录，你也可以通过设置生成目录的最大层级开启这个功能。

### auto2top

切换页面后是否自动跳转到页面顶部。

### homepage

设置首页文件加载路径。适合不想将 README.md 作为入口文件渲染，或者是文档存放在其他位置的情况使用

### basePath

文档加载的根路径，可以是二级路径或者是其他域名的路径。

### coverpage

启用封面页。开启后是加载 \_coverpage.md 文件，也可以自定义文件名。

### logo

网站 logo ，会出现在侧边栏

### name

文档标题，会显示在侧边栏顶部。

### nameLink

点击文档标题后跳转的链接地址。

```js
window.$docsify = {
    nameLink: "/",

    // 按照路由切换
    nameLink: {
        "/zh-cn/": "/zh-cn/",
        "/": "/"
    }
};
```

### noEmoji

禁止 emoji 解析

### mergeNavbar

小屏设备下合并导航栏到侧边栏。

### externalLinkTarget

默认：`_blank`

### routerMode

路由方式默认：hash

```js
window.$docsify = {
    routerMode: "history" // default: 'hash'
};
```

## 进阶

### markdown

修改 `markdown` 解析的配置

### themeColor

替换主题色。利用 CSS3 支持变量的特性，对于老的浏览器有 polyfill 处理。

### alias

定义路由别名，可以更自由的定义路由规则。 支持正则。

示例：

```js
window.$docsify = {
    alias: {
        "/foo/(+*)": "/bar/$1", // supports regexp
        "/zh-cn/changelog": "/changelog",
        "/changelog":
            "https://raw.githubusercontent.com/docsifyjs/docsify/master/CHANGELOG",
        "/.*/_sidebar.md": "/_sidebar.md" // See #301
    }
};
```

### executeScript

是否执行文档中的 `script` 标签，只执行第一个 `script`

> 注意如果执行的是一个外链脚本，比如 jsfiddle 的内嵌 demo，请确保引入 external-script 插件。

### formatUpdated

{docsify-updated}

patterns

```text
{YYYY}: full year; eg: 2017
{YY}: short year; eg: 17
{MM}: month; eg: 04
{DD}: day; eg: 01
{HH}: hours; eg: 06 (24h)
{mm}: minutes; eg: 59
{ss}: seconds; eg: 09
```

示例：

```js
window.$docsify = {
    formatUpdated: "{MM}/{DD} {HH}:{mm}",

    formatUpdated: function(time) {
        // ...

        return time;
    }
};
```

我们可以显示文档更新日期通过 {docsify-updated} 变量. 并且格式化日期通过 formatUpdated。[参考](https://github.com/lukeed/tinydate#patterns)

### noCompileLinks

有时我们不希望 docsify 处理我们的链接,

```js
noCompileLinks: ["/foo", "/bar/.*"];
```

### requestHeaders

设置请求资源的请求头。

```js
window.$docsify = {
    requestHeaders: {
        "x-token": "xxx"
    }
};
```

### ext

资源的文件扩展名。

```js
window.$docsify = {
    ext: ".md"
};
```

### notFoundPage

Load the \_404.md file:

```js
window.$docsify = {
    notFoundPage: true
};
```
