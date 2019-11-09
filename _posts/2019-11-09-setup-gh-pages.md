# GitHub Pages

## Enable GH-Pages
当一user/organization的GitHub Page开启以后，
GitHub Pages的IP地址为:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

如果直接从浏览器访问以上IP地址，你会发现什么结果都没有，因为GitHub Pages的服务器必须通过想要访问的域名<user>.github.io和代码仓库中的CNAME文件来判断从哪里提供网页内容。

例如访问网址https://bob.github.io（实际上通过DNS服务器查询到的IP地址就是上面四个），但GitHub Pages服务器会在`bob`的仓库中寻找：
- 如果bob有名为`bob.github.io`的repository，就显示这个仓库里面的内容（EADME.md/index.html）
- 如果bob的其他某个仓库中，有名为CNAME的文件，且文件内容为`bob.github.io`，将使用该仓库的内容显示https://bob.github.io
- 如果都没有，GitHub 404 Page

> 注意User Pages和Project Pages是独立的：即使bob没有名为`bob.github.io`的repo，我们仍然可以通过`https://bob.github.io/<project>`来访问Project Page

在repo的setting中可以选择Source：
- master branch: README.md或者index.html将被用于显示网页
- master /docs: /docs/README.md或者index.html将被用于显示网页
- gh-pages: index.html将被用于显示网页

## Custom domain

