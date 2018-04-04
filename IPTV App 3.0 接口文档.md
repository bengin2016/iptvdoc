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
| *lang* | string | 用户组语言 空 用户选择模式 / cn 中文 / en 英文 |
| *fee_mode* | integer | 用户组收费模式 0 免费 / 1 收费 |
| *account_expired_at* | string | 用户到期时间, 如果为空则为没有充值 |
| *is_expired* | integer | 用户是否到期 |

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
| *expired_notify_template* | string | 到期后提醒信息 |
| *enable_systempwd* | integer | 是否开启系统设置控制密码 |
| *systempwd* | string | 系统设置密码 |
| *enable_ntp* | integer | 内网NTP时间校准 |
| *kickuser* | integer | 是否开启踢下线功能 |
| *auth* | string | 是否开启免认证 |
| *username* | string | 当前登录用户名 |
| *outdate* | string | 当前用户到期时间 |

### 13.**天干地支纪年法**
* 接口说明：无
* 请求地址：*/api/app/3.0/lunar*
* 请求方式：*GET*
* 参数:
>* 无 

* 响应字段说明:

    "lunar_year": 2017,                 // 农历年		 <br>
    "lunar_month": 4,                   // 农历月		 <br>
    "lunar_day": 10,                    // 农历日		 <br>
    "lunar_month_chinese": "四月",       // (汉字)农历月		<br>
    "lunar_day_chinese": "初十",         // (汉字)农历日  	<br>
    "ganzhi_year": "丁酉",               // (干支)年		 <br>
    "ganzhi_month": "乙巳",              // (干支)月		 <br>
    "ganzhi_day": "壬辰",                // (干支)日		 <br>
    "animal": "鸡",                      // 生肖			 <br>
    "term": "立夏",                      // 节气			 <br>
    "is_leap": false,                    // 是否为闰月		 <br>
    "gregorian_year": 2017,              // 公历年		 <br>
    "gregorian_month": 5,                // 公历月		 <br>
    "gregorian_day": 5,                  // 公历日		 <br>
    "week_no": 5,                        // (数字)星期几		 <br>
    "week_name": "星期五",                // (汉字)星期几		 <br>
    "is_today": false,                   // 是否为今天		 <br>
    "constellation": "金牛"               // 星座		 <br>

### 14.**天气**
* 接口说明：无
* 请求地址：*/api/app/3.0/weather*
* 请求方式：*GET*
* 参数:
>* 无 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *weather* | string | 实时天气情况 |
| *temperature* | string | 实时温度 |
| *temperature_min* | string | 今日最低温度 |
| *temperature_max* | string | 今日最高温度 |

### 15.**电视频道节目单**
* 接口说明：无
* 请求地址：*/api/app/3.0/epg*
* 请求方式：*GET*
* 参数:
>* *name* 电视频道名 从 api/app/2.0/livechannels 接口获取的 channels.channelname 字段 例如: CCTV-1

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | integer | 状态码 |
| *msg* | string | 信息 |
| *items.time* | integer | 节目播放时间 |
| *items.program* | string | 节目名称 |


### 16. **更新查询** 
接口说明：app 更新查询
* 请求地址：*/api/app/3.0/update*
* 请求方式：*GET*
* 参数:
>* *version* 当前版本 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *newversion* | bool | 是否有新版 |
| *update_log* | string | 更新说明 |
| *update_url* | string | app 更新地址 |
| *size* | string | app 大小|
| *version_name* | string | app 版本号|

### 17. **直播列表**
* 接口说明：获取直播列表
* 请求地址：*/api/app/3.0/livechannels*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *updated_at* | integer | 节目单上次更新时间 |
| *items.id* | integer | 节目分类id |
| *items.name* | integer | 节目分类名称 |
| *items.index* | integer | 排序序号 |
| *items.channels.id* | integer | 节目id |
| *items.channels.name* | string | 节目名id |
| *items.channels.channel* | string | 节目名 |
| *items.channels.channelname* | string | 节目名别名 |
| *items.channels.url* | string | 节目m3u8地址 |


### 18. **新版桌面启动器配置**
* 接口说明：获取直播列表
* 请求地址：*/api/launche/1.0/config*
* 请求方式：*GET*
* 参数:
>* 无

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *install* | integer | APK安装全局设置：1 => 允许所有用户安装APK 2=>需要独立授权 0=>禁止所有用户安装APK |
| *supersetting* | integer | 是否允许执行高级系统设置：1=>允许 0=>禁止 |
| *pkgname* | array | 要锁定的应用包名称 |

### 19. **新版桌面启动器模板**
* 接口说明：获取直播列表
* 请求地址：*/api/launche/1.0/theme*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *theme* | string | 主题包下载地址 |
| *notifyurl* | string | 推送回调通知, 在下载完成之后, 请求这个地址通知后台 |

### 20. **新版桌面启动器 默认应用控制**
* 接口说明：获取直播列表
* 请求地址：*/api/launche/1.0/apps*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *items.id* | integer | id |
| *items.title* | string | 按钮名称 |
| *items.app_package_name* | string | 启动的apk包名 |
| *items.app_default_name* | string | 未下载应用显示名称 |
| *items.appurl* | string | apk地址 |

### 21. **新版桌面启动器 应用替换**
* 接口说明：获取直播列表
* 请求地址：*/api/launche/1.0/apps/replace*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |	   
| *total* | integer | 应用总数 |
| *items.id* | integer | id |
| *items.title* | string | 应用名称 |
| *items.target_appname* | string | 要替换的应用包名称 |
| *items.new_appname* | string | 要推送的应用包名称 |
| *items.appversion* | string | 要推送的应用版本 |
| *items.apkurl* | string | 下载地址 |
| *items.notifyurl* | string | 推送回调通知, 在下载完成之后, 请求这个地址通知后台 |

### 22. **新版桌面启动器 推送新应用**
* 接口说明：获取直播列表
* 请求地址：*/api/launche/1.0/apps/push*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |	  
| *total* | integer | 应用总数 |
| *items.id* | integer | id |
| *items.title* | string | 应用名称 |
| *items.app_package_name* | string | 包名 |
| *items.appversion* | string | 要推送的应用版本 |
| *items.apkurl* | string | 下载地址 |
| *items.notifyurl* | string | 推送回调通知, 在下载完成之后, 请求这个地址通知后台 |

### 23. **新版桌面启动器 启动器通知推送**
* 接口说明：获取直播列表
* 请求地址：*/api/launche/1.0/getnotify*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *notify.type* | integer | 通知类型 1文字消息 2图片消息 |
| *items.title* | string | 通知标题 |
| *items.content* | string | 通知内容 如果是图片消息则是图片链接 |
| *items.time* | string | 通知时间 |

### 24. **新版桌面启动器 启动广告管理**
* 接口说明：获取直播列表
* 请求地址：*/api/launche/1.0/ads*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 广告总条数 |
| *items.id* | integer | 广告id |
| *items.time* | integer | 广告播放时间 |
| *items.type* | string | 广告类型 <br> pic 图片广告  <br> video 视频广告 |
| *items.src* | string | 广告地址 |


### 25. **点播支付方式**
* 接口说明：获取支付方式
* 请求地址：*/api/app/3.0/payments*
* 请求方式：*GET*
* 参数:
>* 无

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *items.name* | string | 支付方式名称 |
| *items.enable* | integer | 支付方式是否开启 |

### 26. **点播套餐**
* 接口说明：获取直播列表
* 请求地址：*/api/app/3.0/vod/packages*
* 请求方式：*GET*
* 参数:
>* 无

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 套餐总数 |
| *items.id* | integer | 套餐id |
| *items.name* | string | 套餐名称 |
| *items.thumburl* | string | 套餐缩略图 |
| *items.is_recommend* | integer | 是否推荐 |
| *items.is_hot* | integer | 是否热门 |

### 27. **点播套餐订单提交**
* 接口说明：点播套餐订单提交
* 请求地址：*/api/app/3.0/vod/package/order*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)
>* *payment* 支付方式，获取方法参见 25 支付方式(必填)
>* *pid* 套餐id，获取方法参见 26 点播套餐 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | bool | 状态码|
| *msg* | string | 信息|
| *order_sn* | string | 订单序列号 |

### 28. **点播套餐订单二维码**
* 接口说明：点播套餐订单二维码
* 请求地址：*/api/app/3.0/vod/package/orderqrcode*
* 请求方式：*GET*
* 参数:
>* *order_sn* 订单号 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | bool | 状态码|
| *msg* | string | 信息|
| *url* | string | 订单支付二维码|

### 29. **订单状态检查**
* 接口说明：订单状态检查
* 请求地址：*/api/app/3.0/vod/package/ordercheck*
* 请求方式：*GET*
* 参数:
>* *order_sn* 订单号 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | bool | 状态码|
| *paid* | integer | 是否支付 |

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
| *204* | 点播套餐id为空 |
| *205* | 套餐不存在或者已经下架 |
| *206* | 支付方式不对或禁用 |
| *207* | 订单号不正确 |	     
| *208* | 订单已经支付   |
| *209* | 生成支付订单错误 |
| *210* | 您使用的私钥格式错误，请检查RSA私钥配置 |

##### 3. 电视节目单状态码
| 状态码 |  说明 |	  
| :--: | :-- |
| *300* | 电视频道名不能为空 |
| *301* | 频道不存在 |
| *302* | 频道存在, 但是节目信息匹配不正确 |
| *303* | 节目信息响应为空 |

##### 4. 桌面启动器状态码
| 状态码 |  说明 |	  
| :--: | :-- |
| *400* | 没有任何启用的主题 |
| *401* | 主题压缩包不存在 |
| *402* | 非法请求, 请重启请求主题接口 |
| *403* | 通知 id 不正确 |
