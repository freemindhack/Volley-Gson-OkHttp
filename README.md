**首先声明，我的网络层不是从头开始写，只是封装了（Okio+ Volley +Gson +OkHttp+DisLruCache）。如果是想看从头开始写网络层的大牛们，小弟这实在很是粗浅。可能不能给你带来什么。本文比较适合如我一样的开发新手**

对于个人开发者，或者微型团队开发者来说，一个成熟的网络请求框架将会让你事半功倍。Volley 自2013年 Google I/O大会发布之后，马上便让开发者们为之风靡。没有接触过的同学可以先去了解  [博客链接](http://blog.csdn.net/t12x3456/article/details/9221611)，而本文也是因为它的高扩展性才能有所成。感谢。

而本文是以我搭起这个网络层的思路来叙述的。首先，感谢慕课网的视频教程  [视频链接](http://www.imooc.com/learn/468)，教程中的内容是通过接口的二次封装回调其Respose，给了我很大的启发。

###功能介绍###
请求结果自动反射实体类返回（Volley不提供），加入请求结束调用方法（Volley不提供），简化请求设置优先级，缓存时间，重连策略（Volley自带较为麻烦）。加入图片请求的缓存（本地与内存），替换了饱受病垢的Apache http，改为Okhttp。

**优点：**使得网络请求变得更干净，简介，一定程度上简化了代码量。
**缺点：**图片请求还是很薄弱的，只是单纯做了内存与磁盘缓存，与擦除，并没有提供其他功能。




