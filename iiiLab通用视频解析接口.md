**说明：** 此接口为通用解析接口，支持解析[iiiLab](http://douyin.iiilab.com/)所支持的所有平台视频

**接口地址：** http://service.iiilab.com/video/download

HTTP请求方式：POST

Content-Type: application/x-www-form-urlencoded

**请求参数：**

参数|参数名称|参数说明|是否可空|举例
:---|:---|:---|:---|:---
link|视频链接|要解析的视频页面地址|不可空|http://weibo.com/tv/v/EFSNuE1Ky
timestamp|当前时间戳（毫秒）|发起请求时的时间戳|不可空|1509457938068
sign|签名|[查看接口签名方法](https://github.com/iiiLab/video-api/wiki/%E6%8E%A5%E5%8F%A3%E7%AD%BE%E5%90%8D%E6%96%B9%E6%B3%95)|不可空|2b77c8f00be1c1ec310a8860164835a6
client|客户ID|iiiLab分配给您的客户ID|不可空|996981887a27d721

**成功返回数据：**

![](https://raw.githubusercontent.com/iiiLab/video-api/master/img/common_succ.png)

**失败返回数据：**

![](https://raw.githubusercontent.com/iiiLab/video-api/master/img/common_fail.png)

**返回结果说明：**

* 当retCode为200时代表成功，非200代表失败，如果失败，retDesc为失败原因。
* 如果解析成功，data为解析结果数据，其中video为视频地址，一定有；cover为视频封面地址，可能为空；text为视频标题，可能为空。
  1. 如果是全民K歌的链接，返回结果里还有另外两个字段：videoType(音视频类型，两种可能值：audio, video)，songName(歌曲名称)
* 如果请求失败，retCode为错误代码，retDesc为错误原因，retCode和retDesc是一对多关系，可能出现的错误原因：

<table>
  <tr><th>错误代码（retCode）</th><th>错误原因（retDesc）</th></tr>
  <tr>
  <td rowspan="3">401 （鉴权失败）</td>
  <td>客户ID不存在</td>
</tr>
  <tr>
    <td>签名验证失败</td>
  </tr>
  <tr>
    <td>接口调用额度已用完,请联系站长充值</td>
  </tr>

  <tr>
    <td rowspan="3">400 （参数错误）</td>
    <td>缺少必要参数</td>
  </tr>
  <tr>
    <td>视频链接格式错误</td>
  </tr>
  <tr>
    <td>解析失败,请检查输入的链接页面是否含有视频</td>
  </tr>
</table>