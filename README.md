# Docsify

> [docsify](https://docsify.js.org/#/zh-cn/quickstart) -- A magical documentation site generator.

## 简介

Docsify 是一个动态生成文档网站的工具

### 特点

1.  不会生成将 `.md` 转成 `.html` 文件，所有转换工具都是在运行时进行
2.  可以直接发布
3.  轻量
4.  智能的全文搜索
5.  提供多套主题
6.  丰富的 API
7.  支持 Emoji
8.  兼容 IE10+
9.  支持 SSR (example)
10. 实时预览

## 搭建文档

### 起步

1.  使用 `docsify-cli` 工具，可以方便创建以及本地预览

    `npm i docsify-cli -g`

2.  初始化项目

    `docsify init ./[filename]`

3.  目录结构

    -   `index.html` 入口文件
    -   `README.md` 会做为主页面内容渲染
    -   `.nojekyll` 用于阻止 GitHub Pages 会忽略掉下划线开头的文件

    直接编辑 `README.md` 就能更新网站内容

4.  本地预览网站

    `docsify serve [filename]` 可以方便的预览效果，而且提供 LiveReload 功能，可以让实时的预览。

### 页面编辑

1.  页面装载

    渲染后页面装载，默认在:

    _index.html_

    ```html
    <div id="app">加载中</div>
    ```

    加载结束后，会替换标签的内容，所以这里可以放加载的 `Loading`

    如果希望修改装载的容器，可以这样修改：

    _index.html_

    ```html
    <div data-app id="main">加载中</div>

    <script>
        window.$docsify = {
            el: "#main"
        };
    </script>
    ```
