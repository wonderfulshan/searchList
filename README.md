# 仿百度的自动下拉搜索框
## JSONP跨域请求数据
这个demo 的核心是数据的获取，也就是说当用户输入一些词汇的时候，你怎么去找到那些联想词。百度提供了一个官方接口http://www.baidu.com/su?&wd=。<br>如果是用 ajax 去调用，根据同源策略就无法获取数据，所以 jsonp 是个很好的办法。
## 一些优化
* 页面重绘回流优化<br>
在JS中创建一个新ul，并且把li添加进去，最后把新ul和旧ul进行替换。把多次回流合并成一次
* 事件委托<br>
在ul中绑定click事件，减少了事件注册，节省了内存占用，大大提高了性能。同时让每个动态添加的li都能绑定事件。
* 预防xss<br>
转译html代码，防止恶意JS脚本注入：
* 内存泄漏<br>
把变量值设为null

[demo](https://wonderfulshan.github.io/searchList)

