# 易语言网页访问BUG
尝试在易语言中获取并输出`test.txt`的内容吧。

URL：

国内源：

[https://cdn.jsdelivr.net/gh/voltachan/ebug@master/test.txt](https://cdn.jsdelivr.net/gh/voltachan/ebug@master/test.txt)

国外源：

[https://github.com/voltachan/ebug/raw/master/test.txt](https://github.com/voltachan/ebug/raw/master/test.txt)

# 结果
方式 | 结果
:-: | :-: 
Chrome 浏览器|成功，返回`Can You See Me ? !@#$%^&*()`
网页_访问S|***失败，返回空字符串***
网页_取网页源码|***失败，返回空字符串***

初步判断为`到文本`函数存在BUG，一旦字节集中出现00字节就会截断。

> 使用如下方法可以成功获取（删除首00字节）（[@longsui48](https://bbs.125.la/home.php?mod=space&uid=448246)）：
> 
> `到文本 (字节集_替换 (网页_访问_对象 (“https://cdn.jsdelivr.net/gh/voltachan/ebug@master/test.txt”), 1, 1, {  }))`
