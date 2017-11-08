# IPTV App 2.0 接口文档

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

### 2. **用户信息**
* 接口说明：获取登录用户信息。
* 请求地址：*/api/app/2.0/userinfo*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | integer | 状态码 |
| *id* | integer | 用户id |
| *username* | integer | 用户帐号 |
| *status* | integer | 用户帐号是否锁定 |
| *group_name* | string | 用户组名 |
| *expiration* | date | 用户到期时间 |
| *mac_address* | string | 绑定的无线网卡 |

### 3. **广告接口**
* 接口说明：获取app相关广告信息。
* 请求地址：*/api/app/2.0/ads*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
>如果设置为播放2次 间隔时间为10分钟则2次播放完成为20分钟，执行完后开始下一条的播放。 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *befor_play* | object | 映前广告 |		
| *befor_play.total* | string| 映前广告个数 |
| *befor_play.item.src* | string| 映前广告访问地址 |
| *befor_play.item.countdown* | string| 映前广告倒计时 |
| *appad* | object | app启动广告 |		
| *appad.total* | string| app启动广告个数 |
| *appad.item.src* | object | app启动广告访问地址 |
| *appad.item.countdown* | object | app启动广告倒计时 |
| *captionad* | array | 字幕广告(多个)|
| *captionad.total* | array | 字幕广告(多个)|
| *captionad.items[0].playtimes* | integer  | 字幕广告播放次数|
| *captionad.items[0].content* | string | 字幕广告内容|
| *captionad.items[0].interval* | integer | 字幕广告间隔时间|


### 4. **首页展示资源**
* 接口说明：获取app首页展示资源。
* 请求地址：*/api/app/2.0/portalhome*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *items.vodid* | integer | 视频id |
| *items.cid* | integer | 视频分类id |
| *items.category* | integer | 视频分类名 |
| *items.name* | string | 视频名称 |
| *items.poster* | string | 视频海报 |

### 5. **直播列表**
* 接口说明：获取直播列表
* 请求地址：*/api/app/2.0/livechannels*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
> 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *id* | integer | 节目分类id |
| *name* | integer | 节目分类名称 |
| *index* | integer | 排序序号 |
| *channels.id* | integer | 节目id |
| *channels.name* | string | 节目名id |
| *channels.channel* | string | 节目名 |
| *channels.channelname* | string | 节目名别名 |
| *channels.url* | string | 节目m3u8地址 |

### 6. **视频详情**
* 接口说明：获取视频详情
* 请求地址：*/api/app/2.0/vodinfo*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)
>* *vodid* 视频id

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *id* | integer | 视频id |
| *name* | string | 视频名称 |
| *rank* | float | 评分 |
| *poster* | string | 海报 |
| *abstract* | string | 简介 |
| *tags* | string | 标签 |
| *actor* | string | 演员 |
| *region* | string | 地区 |
| *year* | integer | 年份 |
| *vodlist.title* | string | 集数、标题、期数 |
| *vodlist.url* | string | 播放地址 |

### 7. **视频地区**
* 接口说明：获取视频地区详情
* 请求地址：*/api/app/2.0/regions*
* 请求方式：*GET*
* 参数:
>* 无 

### 8. **视频分类**
* 接口说明：获取视频分类
* 请求地址：*/api/app/2.0/vodcategories*
* 请求方式：*GET*
* 参数:
>* 无 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *id* | integer | 视频id |
| *name* | string | 视频名称 |
| *poster* | string | 海报 |

### 9. **视频分类标签**
* 接口说明：获取视频分类
* 请求地址：*/api/app/2.0/categorytags*
* 请求方式：*GET*
* 参数:
>* *category* 分类id, 获取方法参见 视频分类 /api/app/2.0/vodcategories

### 10. **视频列表** 
接口说明：获取视频列表
* 请求地址：*/api/app/2.0/vodlist*
* 请求方式：*GET*
* 参数:
>* *page* 页数 
>* *perpage* 每页记录条数 
>* *keywords* 关键字 
>* *category* 分类id 
>* *tag* 分类标签 
>* *region* 影片地区 
>* *year* 年份 
>* *order* 排序 （hits 点击排序/star 评分排序/new 时间先后倒序）

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 总条数 |
| *perpage* | string | 分页记录数 |
| *page* | string | 页数 |
| *pages* | string | 总页数 |
| *items.id* | integer | 视频id |
| *items.name* | string | 视频名称 |
| *items.poster* | string | 视频海报 |
| *items.rank* | string | 视频评分 |
| *items.category* | string | 视频分类 |
| *items.abstract* | string | 视频简介 |
| *items.tags* | string | 视频标签 |
| *items.actor* | string | 导演 |
| *items.region* | string | 所属地区 |
| *items.year* | string | 视频年份 |
| *items.totalsize* | string | 视频文件总大小 |
| *items.created_at* | string | 视频资源创建时间 |
| *items.playtimes* | string | 播放次数 |

### 11. **视频相关** 
接口说明：获取视频相关视频
* 请求地址：*/api/app/2.0/relatedvods*
* 请求方式：*GET*
* 参数:
>* *vodid* 视频id 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *id* | integer | 视频id |
| *name* | string | 视频名称 |
| *poster* | string | 视频海报 |

### 12. **更新查询** 
接口说明：app 更新查询
* 请求地址：*/api/app/2.0/update*
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


### 13. **心跳检测** 
接口说明：获取视频相关视频
* 请求地址：*/api/app/2.0/heartbeat*
* 请求方式：*GET*
* 参数:
>* *token* 当前token

* 说明:
>* token 有效不会刷新token，如果过期1小时内，会刷新token，否则需要重新登录获取token 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | string | 状态码 |
| *token* | string | 令牌 |
| *expired_at* | string | 令牌到期时间 |

### 14. **启动动画获取接口** 
接口说明：获取视频相关视频
* 请求地址：*/api/app/2.0/getbootanimation*
* 请求方式：*GET*
* 参数:
>* 无

* 说明:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *version* | string | 版本号 |
| *src* | string | 启动动画 bootanimation.zip 下载地址 |

### 15. **app相关图片获取接口** 
接口说明：获取视频相关视频
* 请求地址：*/api/app/2.0/getpics*
* 请求方式：*GET*
* 参数:
>* 无

* 说明:
>* 无	  

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *backgroundimage* | string | 背景图 |
| *btn1* | string | 按钮1 |
| *btn2* | string | 按钮2 |
| *btn3* | string | 按钮3 |
| *btn4* | string | 按钮4 |
| *btn1_package* | string | 按钮1 App 入口点 |
| *btn2_package* | string | 按钮2 App 入口点 |
| *btn4_package* | string | 按钮4 App 入口点 |

### 16. **启动器通知接口** 
接口说明：获取视频相关视频
* 请求地址：*/api/app/2.0/getnotify*
* 请求方式：*GET*
* 参数:
>* 无

* 说明:
>* 如无 AD_Launcher 模块权限, 则无权限访问接口

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *title* | string | 消息标题	 |
| *time* | string | 发布时间 |
| *content* | string | 发布类型 1=> 文字消息, 2=>图片消息 |
| *type* | string | 消息内容 |
| *picture* | string | 图片消息的图片 |

### 17. **App 包管理** 
接口说明：获取 App 安装包
* 请求地址：*/api/app/2.0/apkinstall*
* 请求方式：*GET*
* 参数:
>* 无

* 说明:
>* 如无 AD_Launcher 模块权限, 则无权限访问接口

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *iptvdel* | string | 电视直播包名 |
| *voddel* | string | 视频点播包名 |
| *install* | string | 安装包地址 |
| *apk_pack* | string | 包名称 |

### 18. **7 日更新视频** 
接口说明：获取 7 日更新视频
* 请求地址：*/api/app/2.0/lastupdate
* 请求方式：*GET*
* 参数:
>* 无

* 说明:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *id* | integer | 视频id |
| *name* | string | 视频名称 |
| *poster* | string | 视频海报 |
| *rank* | string | 视频评分 |
| *category* | string | 视频分类 |
| *abstract* | string | 视频简介 |
| *tags* | string | 视频标签 |
| *actor* | string | 导演 |
| *region* | string | 所属地区 |
| *year* | string | 视频年份 |
| *totalsize* | string | 视频文件总大小 |
| *created_at* | string | 视频资源创建时间 |
| *playtimes* | string | 播放次数 |

### 19. **apk首页管理的接口** 
接口说明：apk首页管理的接口
* 请求地址：*/api/app/2.0/indexmanage*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
>* 无

* 响应字段说明:	 
>* 无

### 20. **首页字幕** 
接口说明：首页字幕
* 请求地址：*/api/app/2.0/appcaption*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 说明:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 字幕总数 |
| *items* | array | 字幕内容 |


### 21. **手机客户端启动LOGO图片管理**
  
接口说明：启动LOGO图片管理
* 请求地址：*/api/mobile/startup*
* 请求方式：*GET*
* 参数:
>* 无 

* 说明:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 图片总数 |
| *name* | string | 图片名称 |
| *url* | string | 图片地址 |

### 22. **APP轮播图片管理**
  
接口说明：手机客户端APP轮播图片管理
* 请求地址：*/api/mobile/rotation*
* 请求方式：*GET*
* 参数:
>* 无 

* 说明:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 图片总数 |
| *name* | string | 图片名称 |
| *url* | string | 图片地址 |

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

##### 2. 点播相关状态码
| 状态码 |  说明 |	  
| :--: | :-- |
| *200* | vodid 不能为空 |
| *201* | vodid不对，视频不存在 |

##### 3. 酒店版状态码
| 状态码 |  说明 |	  
| :--: | :-- |
| *300* | 商品未上架或者商品不存在 |
| *301* | 商品数量不对 |
| *302* | 订单不存在 |

