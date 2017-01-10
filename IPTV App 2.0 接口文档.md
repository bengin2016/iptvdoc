# IPTV App 2.0 接口文档

> 测试服务器 http://58.58.66.74:15180/

### 1.**用户登录**
* 接口说明：用于给验证设备账号。
* 请求地址：*/api/app/2.0/userlogin*
* 请求方式：*GET*
* 参数:
>* *username* 用户名 (必填)
>* *mac_address1* 无线网卡mac地址 (必填)
>* *mac_address2* 有线网卡mac地址 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | bool | 状态码|
| *msg* | string | 信息|
| *token* | string | 如果登录成功会返回token|

### 2. **用户信息**
* 接口说明：获取登录用户信息。
* 请求地址：*/api/app/2.0/userinfo*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)


* 说明:
>无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | integer | 状态码 |
| *id* | integer | 用户id |
| *username* | integer | 用户帐号 |
| *status* | integer | 用户帐号是否锁定 |
| *group_name* | string | 用户组名 |
| *end_time* | string | 用户到期时间 |
| *mac_address1* | string | 绑定的无线网卡 |
| *mac_address2* | string | 绑定的有线网卡 |

### 3. **广告接口**
* 接口说明：获取app相关广告信息。
* 请求地址：*/api/app/2.0/ads*
* 请求方式：*GET*
* 参数:
>* *无*

* 说明:
>如果设置为播放2次 间隔时间为10分钟则2次播放完成为20分钟，执行完后开始下一条的播放。 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *befor_play* | object | 映前广告 |
| *befor_play.src* | string| 映前广告访问地址 |
| *befor_play.countdown* | string| 映前广告倒计时 |
| *appad* | object | app启动广告 |
| *appad.src* | object | app启动广告访问地址 |
| *appad.countdown* | object | app启动广告倒计时 |
| *captionad* | array | 字幕广告(多个)|
| *captionad[0].playtimes* | integer  | 字幕广告播放次数|
| *captionad[0].content* | string | 字幕广告内容|
| *captionad[0].interval* | integer | 字幕广告间隔时间|


### 4. **首页展示资源**
* 接口说明：获取app首页展示资源。
* 请求地址：*/api/app/2.0/portalhome*
* 请求方式：*GET*
* 参数:
>* *无*

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *items.id* | integer | 视频id |
| *items.cid* | integer | 视频分类id |
| *items.category* | integer | 视频分类id |
| *items.name* | string | 视频分类名称 |
| *items.poster* | string | 视频海报 |

