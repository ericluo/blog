---
tags: jekyll
---

## jekyll-gist插件

安装好`gist-it`插件后，设置好对应的`token`，就可以在`Atom`中直接 **gist** 代码片段了。

接下来，就需要在`markdown`文档中引用刚刚创建的`gist`。

{% raw %}
  {% gist ericluo/8a94b03781aaa65941b6978c9b89c578 %}
{% endraw %}

{% gist ericluo/8a94b03781aaa65941b6978c9b89c578 %}

**Tips:** 在上面的例子中，使用了{% raw %}标签来对代码块中的`Liquid`代码片段进行封装。如果不这样做，其将会被`Liquid`进行解析并翻译，这可不是我们想要的结果。
 {: .notice--primary}

## jekyll应用疑难问题

在Windows上启动`jekyll`以后，会碰到的问题如下：

> GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.

> Error: SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed

> Error: Run jekyll build –trace for more information.

[解决方法](https://www.hieule.info/programming/fix-errors-github-metadata-ssl-certificate-running-jekyll-serve/)
