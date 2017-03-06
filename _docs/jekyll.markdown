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
