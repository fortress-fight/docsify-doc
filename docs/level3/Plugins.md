# 插件

## 代码拷贝

引入链接

<!-- index.html -->

```js
<script src="//unpkg.com/docsify-copy-code" />
```

## 搜索功能

1.  引入链接

    ```html
    <script src="//unpkg.com/docsify/lib/plugins/search.js"></script>
    ```

2.  添加配置项

    ```js
    window.$docsify = {
        search: "auto", // 默认值

        search: [
            "/", // => /README.md
            "/guide", // => /guide.md
            "/get-started", // => /get-started.md
            "/zh-cn/" // => /zh-cn/README.md
        ],

        // 完整配置参数
        search: {
            maxAge: 86400000, // 过期时间，单位毫秒，默认一天
            paths: [], // or 'auto'
            placeholder: "Type to search",

            // 支持本地化
            placeholder: {
                "/zh-cn/": "搜索",
                "/": "Type to search"
            },

            noData: "No Results!",

            // 支持本地化
            noData: {
                "/zh-cn/": "找不到结果",
                "/": "No Results"
            },

            // 搜索标题的最大程级, 1 - 6
            depth: 2
        }
    };
    ```

    示例：

    ```json
    search: {
        maxAge: 86400000, // 过期时间，单位毫秒，默认一天
        paths: [], // or 'auto'
        placeholder: 'Type to search',
        noData: 'No Results!',
        // 搜索标题的最大程级, 1 - 6
        depth: 2
    }
    ```

3.  Edit On Git

    添加配置：

    ```js
    window.$docsify = {
        plugins: [
            function(hook, vm) {
                hook.beforeEach(function(html) {
                    if (/githubusercontent\.com/.test(vm.route.file)) {
                        url = vm.route.file
                            .replace("raw.githubusercontent.com", "github.com")
                            .replace(/\/master/, "/blob/master");
                    } else {
                        // Git 地址
                        url = "******/edit/master/" + vm.route.file;
                    }
                    var editHtml = "[:memo: Edit Document](" + url + ")\n";

                    return (
                        editHtml +
                        html +
                        "\n\n----\n\n" +
                        '<a href="https://docsify.js.org" target="_blank" style="color: inherit; font-weight: normal; text-decoration: none;">Powered by docsify</a>'
                    );
                });
            }
        ]
    };
    ```
