# IPTV App 3.0 接口文档

> 测试服务器 http://my.tmos.cn:15180/

### 1.**用户登录**
* 接口说明：用于给验证设备账号。
* 请求地址：*/api/app/2.0/userlogin*
* 请求方式：*GET*
* 参数:
>* *username* 用户名 (必填)
>* *mac_address* 网卡mac地址 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | bool | 状态码|
| *msg* | string | 信息|
| *token* | string | 如果登录成功会返回token|
| *expired_at* | string | 如果登录成功会返回token失效的时间戳，token失效需要访问心跳接口刷新token |

### 2.**首页幻灯片**
* 接口说明：无
* 请求地址：*/api/app/3.0/indexrotations*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 幻灯片总条数 |
| *interval* | integer | 幻灯片播放间隔时间 |
| *items.id* | string | 幻灯片id |
| *items.src* | string | 幻灯片图片地址 |

### 3.**换台图片广告**
* 接口说明：无
* 请求地址：*/api/app/3.0/changechannelads*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 图片广告总条数 |
| *items.id* | integer | 图片广告id |
| *items.src* | string | 图片广告地址 |
| *items.time* | string | 图片广告播放间隔时间 |
| *items.position* | string | 图片广告位置 <br> top_left 左上角 <br>top_right 右上角 <br>bottom_left 左下角 <br>bottom_right 右下角 <br>bottom_center 下部居中  |
| *items.height* | string | 图片广告高度 |
| *items.width* | string | 图片广告宽度 |

### 4.**apk启动广告**
* 接口说明：无
* 请求地址：*/api/app/3.0/apkstartupads*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 广告总条数 |
| *items.id* | integer | 广告id |
| *items.time* | integer | 广告播放时间 |
| *items.type* | string | 广告类型 <br> pic 图片广告  <br> video 视频广告 |
| *items.src* | string | 广告地址 |

### 5.**播放前广告**
* 接口说明：无
* 请求地址：*/api/app/3.0/adsbeforeplay*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 广告总条数 |
| *items.id* | integer | 广告id |
| *items.time* | integer | 广告播放时间 |
| *items.type* | string | 广告类型 <br> pic 图片广告  <br> video 视频广告 |
| *items.src* | string | 广告地址 |

### 6.**直播字幕**
* 接口说明：无
* 请求地址：*/api/app/3.0/livecaptions*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 字幕总条数 |
| *items.id* | integer | 字幕id |
| *items.time* | integer | 字幕播放次数 |
| *items.bgcolor* | string | 字幕背景颜色 |
| *items.fontcolor* | string | 字幕字体颜色 |
| *items.content* | string | 字幕内容 |
| *settings.interval* | integer | 加载下一条字幕间隔时间 |
| *settings.caption_loop_type* | integer | 字幕循环模式<br> 1 全部播放完毕关闭显示<br> 2 播放完毕自动循环播放 |
| *settings.caption_load_type* | integer | 字幕加载模式：<br> 1 换台继续播放<br> 2 换台重新播放 |

### 7.**一级页面字幕**
* 接口说明：无
* 请求地址：*/api/app/3.0/anothercaptions*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 字幕总条数 |
| *items.id* | integer | 字幕id |
| *items.content* | string | 字幕内容 |
| *settings.interval* | integer | 加载下一条字幕间隔时间 |
| *settings.caption_loop_type* | integer | 字幕循环模式<br> 1 全部播放完毕关闭显示<br> 2 播放完毕自动循环播放 |
| *settings.caption_load_type* | integer | 字幕加载模式：<br> 1 换台继续播放<br> 2 换台重新播放 |

### 8.**背景图片**
* 接口说明：无
* 请求地址：*/api/app/3.0/appbgpics*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *item.id* | integer | 背景图片id |
| *item.title* | string | 背景图片名称 |
| *item.src* | string | 背景图片地址 |

### 9.**vip 影城**
* 接口说明：无
* 请求地址：*/api/app/3.0/videos*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)
>* *perpage* 分页数默认为10 (选填)
>* *keywords* 关键字 支持拼音首字母 (选填)
>* *category* 分类id 1 电影 / 2 电视剧 (选填)
>* *last_id* 上一个记录集的最后一个影片id, 用于取得下一个影片记录集  (选填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | integer | 状态码|
| *msg* | string | 信息 |
| *total* | integer | 影片总数 |
| *items.id* | integer | 影片id |
| *items.name* | string | 影片名称 |
| *items.category* | string | 分类 |
| *items.tags* | string | 标签 |
| *items.rank* | string | 评分 |
| *items.year* | string | 年份 |
| *items.region* | string | 地区 |
| *items.actor* | string | 导演 |
| *items.poster* | string | 图标图片地址 |
| *items.background* | string | 背景图片地址 |
| *items.description* | string | 简介 |

### 10.**vip 影城影片详情**
* 接口说明：无
* 请求地址：*/api/app/3.0/video/detail*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)
>* *id* 影片id (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | integer | 状态码|
| *msg* | string | 信息 |
| *total* | integer | 影片总数 |
| *items.index* | integer | 影片索引 |
| *items.url* | string | 影片地址 |

### 11.**轮播频道**
* 接口说明：无
* 请求地址：*/api/app/3.0/lunbo*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 轮播频道总数 |
| *item.id* | integer | 轮播频道id |
| *item.name* | string | 轮播频道名称 |
| *item.content.index* | string | 轮播频道视频索引 |
| *item.content.name* | string | 轮播频道视频名称 |
| *item.content.url* | string | 轮播频道视频地址 |

### 12.**全局设置**
* 接口说明：无
* 请求地址：*/api/app/3.0/config*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *admodel* | integer | 点播映前广告播放模式 |
| *viptheater* | integer | 是否开放VIP影院 |
| *enable_notify_before_expire* | integer | 是否启用到期前提醒 |
| *enable_expired_notify* | integer | 是否启用到期后提醒 |
| *days_before_expired* | integer | 到期前提醒天数 |
| *notify_before_expire_template* | string | 到期前提醒信息 |
| *enable_expired_notify_template* | string | 到期后提醒信息 |
| *enable_systempwd* | integer | 是否开启系统设置控制密码 |
| *systempwd* | string | 系统设置密码 |
| *enable_ntp* | integer | 内网NTP时间校准 |
| *kickuser* | integer | 是否开启踢下线功能 |
| *auth* | string | 是否开启免认证 |
| *username* | string | 当前登录用户名 |
| *outdate* | string | 当前用户到期时间 |

####  **状态码说明** 

##### 全局状态码 
| 状态码 |  说明 |	  
| :--: | :-- |
| 0 | 正常 |
| -1 | 无权访问 |

##### 1. 用户相关状态码
| 状态码 |  说明 |	  
| :--: | :-- |
| *100* | 用户名不能为空 |
| *101* | 用户不存在 |
| *102* | mac地址不能为空 |
| *103* | 用户不存在 |
| *104* | token 不能为空 |
| *105* | token 已过期, 访问心跳接口可以刷新token |
| *106* | token 过期失效，需要重新登录|
| *107* | 账号已过期 |
| *108* | 账号被禁用 |
| *109* | 账号没有 vip 影城权限 |

##### 2. VIP影城相关状态码
| 状态码 |  说明 |	  
| :--: | :-- |
| *200* | vip 影片id 不能为空 |
| *201* | 账号没有 vip 影城权限 |
| *202* | vip 影片不存在 |
| *203* | vip 影城没有开启 |