# 基础配置信息

## 简单型

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>Document</title>
        <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
        <meta name="description" content="Description" />
        <meta
            name="viewport"
            content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"
        />
        <link rel="stylesheet" href="//unpkg.com/docsify/themes/vue.css" />
    </head>

    <body>
        <div id="app"></div>
        <script>
            window.$docsify = {
                name: "docsify-css",
                repo: "git@github.com:fortress-fight/css.git",
                loadSidebar: true,
                subMaxLevel: 3,
                formatUpdated: "{MM}/{DD} {HH}:{mm}",
                auto2top: true,

                search: {
                    maxAge: 86400000, // 过期时间，单位毫秒，默认一天
                    paths: [], // or 'auto'
                    placeholder: "Type to search",
                    noData: "No Results!",
                    // 搜索标题的最大程级, 1 - 6
                    depth: 2
                },
                plugins: [
                    function(hook, vm) {
                        hook.beforeEach(function(html) {
                            if (/githubusercontent\.com/.test(vm.route.file)) {
                                url = vm.route.file
                                    .replace(
                                        "raw.githubusercontent.com",
                                        "github.com"
                                    )
                                    .replace(/\/master/, "/blob/master");
                            } else {
                                url = "******/edit/master/" + vm.route.file;
                            }
                            var editHtml =
                                "[:memo: Edit Document](" + url + ")\n";

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
        </script>
        <script src="//unpkg.com/docsify/lib/docsify.min.js"></script>
        <script src="//unpkg.com/docsify-copy-code"></script>
        <script src="//unpkg.com/docsify-pagination/dist/docsify-pagination.min.js"></script>
        <script src="//unpkg.com/docsify/lib/plugins/search.js"></script>
    </body>
</html>
```
