---
tags: Python
---

{% include toc %}

## 时间转换

在Python中经常要用到的时间格式的转换，如从字符串转换为日期格式，或是从日期格式转换为字符串，还有时候需要将整数数值型转换为字符串。可以借助于标准库 `datetime`中的相关函数来实现。

```python
import datetime
d = datetime.datetime.strptime(str(20151231), '%Y%m%d')
```

## 函数式编程

> map filter zip enumerate range str tuple type


## `Pandas`

`Pandas`中常用的对象主要有`DataFrame`、`Series`和`Panel`，3个不同对象之间提供了相应的方法可以相互转化。3个对象中比较好用的方法记录如下：

- Series
  - value_counts 统计序列中不同值的个数
  - size


- DataFrame
  - fillna 将`NA`替换为缺省值
  - sort_index
  - groupby(['year', 'sex'])
  - pivot_table('births', rows='year', cols='sex', aggfunc=sum)


### `plotly`

在使用`Pandas`进行数据分析研究时，需要用到`dataframe.plot`的函数来进行绘图，但是用该函数绘图使用中文时需要做特殊的设置，非常不方便。网上看到有推荐使用`plotly`的，该包可以将生产的图片自动地保存到云上，这样在文档中直接插入对应的链接就可以了。**更重要的是，还可以对图像进行动态的更新，而不需要对原有文档进行更新，倒是可以省不少事。**

`plotly`账号信息（在ricequant上的文档中有记录）：

### 在文章中引用图像

可以通过`iframe`技术来在文章中直接引用生产的图像文件。

```html
<iframe width="800" height="600" frameborder="0" scrolling="no"  src="//plot.ly/~luowenbo/2.embed"></iframe>
```

**并可以用[参数](http://help.plot.ly/embed-graphs-in-websites/#step-8-customize-the-iframe)来控制图像中的相关元素。**

![](http://7xonmk.com1.z0.glb.clouddn.com/2017-03-04_13-05-47.png)

### FAQ

- 如何将Panel降维扁平化

> 可以通过 `xs`、`minor_xs`或`major_xs`函数将三维的`Panel`转换为两维的`Dataframe`

## Jupyter

`Jupyter Notebook` 是一个很方便的学习、研究和文档撰写平台。通过这两天的研究，已经初步掌握了其日常的用法。通过在 `Markdown` 文档中嵌入 `Python` 的脚本，可以通过后者来生成动态的图片、表格，甚至还可以增加一些动态的交互效果。

### 设置主页目录

默认状态下，`Notebook` 的 HOME 目录设置在当前用户主目录下。该目录混杂了所有用户相关的文件信息，比较杂乱。而且，该目录下的文件没有进行自动云端同步。不同电脑之间的研究文档同步只能通过手动操作，比较繁琐。

更好的解决方案是设置专用的 HOME 目录，并将该目录设置在 `OneDrive` 下。具体操作过程如下：

- 通过如下命令生成配置文件。

```bash
jupyter notebook --generate-config
```

该命令会在用户主目录下生成一个配置文件: ".jupyter/jupyter_notebook_config.py"

- 在该配置文件中设置文档目录, **注意设置中的双斜线**

```python
c.NotebookApp.notebook_dir = u"C:\\Usersi\\CBRC\\OneDrive\\workspace\\investment"
```

- 重启 `Jupyter`，就可以看到 HOME 目录已经更新了。

## Links

- [pandas](http://pandas.pydata.org)
- [Python中文开发者社区](http://pythontab.com)
- [Pands in 15 minutes](http://www.cnblogs.com/chaosimple/p/4153083.html)
