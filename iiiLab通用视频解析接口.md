接口地址：http://service.iiilab.com/video/download

HTTP请求方式：POST

Content-Type: application/x-www-form-urlencoded

请求参数：

参数|参数名称|参数说明|是否可空|举例
:---|:---|:---|:---|:---
link|视频链接|要解析的视频页面地址|不可空|http://weibo.com/tv/v/EFSNuE1Ky
timestamp|当前时间戳（毫秒）|发起请求时的时间戳|不可空|1509457938068
sign|签名|签名方法见下文|不可空|2b77c8f00be1c1ec310a8860164835a6
client|客户ID|iiiLab分配给您的客户ID|不可空|996981887a27d721

成功返回数据：

![](https://raw.githubusercontent.com/iiiLab/video-api/master/img/common_succ.png)

失败返回数据：

![](https://raw.githubusercontent.com/iiiLab/video-api/master/img/common_fail.png)


