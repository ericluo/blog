---
tags: jekyll
---

## [Liquid](https://shopify.github.io/liquid/)

`Jekyll`使用了`Liquid`语言作为模板语言，其主要有三种类型：

- object {% raw %}`{{ }}`{% endraw %} 可以直接生成`html`字符串内容
- Tag {% raw %}`{% %}`{% endraw %}
  - Control Flow: if, unless, elsif/else, case/when
  - Iteration: for, break, continue, for(limit, offset, range, reversed), cycle, tablerow
  - Variable: assign, capture
- Filter `|` map, sort, uniq, etc


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

### SSL认证
在Windows上启动`jekyll`以后，会碰到的问题如下：

> GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.

> Error: SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed

> Error: Run jekyll build –trace for more information.

[解决方法](https://www.hieule.info/programming/fix-errors-github-metadata-ssl-certificate-running-jekyll-serve/)

主要解决的问题有：

1. 下载证书并设置相关的环境变量
2. 设置`GitHub Token`相关的环境变量

### 文章无法显示

今天碰到一个问题，新写的帖子再本地和`GitHub`上均无法显示，好像是丢失了。但是查看文件缺失在哪里。最后最终到原因在于在`_config.yml`中设置的时区，导致其认为是一个将来的帖子，自动忽略了，没有生产对应的文件。

还有一个坑是总是报错说错误地使用了`post_url`这个`Tag`，即：

正确的写法：<http://jekyllrb.com/docs/templates/>

    {% post_url file_name %}  

错误的写法：

    {{ post_url filename }}

但是，将错误的写法改正后，系统还是报原来的错误，可能是缓存的问题。这些错误缺失是莫名其妙！
