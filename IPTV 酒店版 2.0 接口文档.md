# IPTV 酒店版 App 2.0 接口文档

> 测试服务器 http://my.tmos.cn:15280/

### 1.**酒店设置** 
* 接口说明：获取酒店商城分类信息
* 请求地址：*/api/2.0/hotel/config*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/category?token=c733a686306d8c9744631ab498d874b1

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *wifi* | string | 0 wifi 关闭 <br>  1 wifi 开启  |
| *wifiname* | string | wifi 热点名称  |
| *wifipwd* | string | wifi 密码 |
| *timezone* | string | 时区设置 |
| *pwd* | string | 系统设置解锁密码 |
| *startup_app* | string | 互动电视启动包名 |
| *bgmode* | string | 背景显示设置 <br> 1 静态图模式 <br>2 幻灯片模式 <br> 3 视频模式 |
| *bgpics* | string | 背景显示设置为静态图模式或幻灯片模式的图片地址 |
| *bgvideo* | string | 背景显示设置为视频模式时候的视频地址 |
| *src* | string | 顶标图地址 |
| *src2* | string | 底标图地址 |
| *src3* | string | 背景图地址 |
| *lang* | object | 多语言设置项 |
| *lang.name* | string | 语言名称 |
| *lang.alias* | string | 语言简写别名, 可以用于程序判定 |
| *lang.enable* | string | 语言是否启用 |
| *lang.text1* | string | 扩展显示1 |
| *lang.text2* | string | 扩展显示2 |
| *lang.text3* | string | 底部文字信息 |
| *payments* | object | 启用的支付方式 |

* 响应范例:
<pre>
{
    "rotation_switch_time": "1",
    "rotaion_type": "2",
    "about_rotation_switch_time": "3",
    "around_rotatio_switch_time": "4",
    "wifi": "1",
    "wifiname": "5",
    "wifipwd": "6",
    "paytype": "1",
    "timezone": "6",
    "pwd": "7",
    "startup_app": "8",
    "noticeshow": "1",
    "city": "北京市",
    "bgmode": "2",
    "bgvideo": "http://iptv4hotel.tos.com/manage#/hotel2/1/1.mp4",
    "src": "http://iptv4hotel.tos.com/upload/2018/05/13/p5af811ff2173e.jpg",
    "src2": "http://iptv4hotel.tos.com/upload/2018/05/13/p5af81204c2cd0.jpg",
    "src3": "http://iptv4hotel.tos.com/upload/2018/05/13/p5af81209a19f8.jpg",
    "bgpics": [
        {
            "src": "http://iptv4hotel.tos.com/upload/2018/05/14/p5af943478b420.jpg"
        },
        {
            "src": "http://iptv4hotel.tos.com/upload/2018/05/14/p5af9434d8c39c.jpg"
        },
        {
            "src": "http://iptv4hotel.tos.com/upload/2018/05/14/p5af9435aca57c.jpg"
        },
        {
            "src": "http://iptv4hotel.tos.com/upload/2018/05/14/p5af9435fa4c1a.jpg"
        }
    ],
    "lang": [
        {
            "name": "中文简体",
            "alias": "cns",
            "enable": "1",
            "welcome": "1",
            "text1": "2",
            "text2": "3",
            "text3": "4"
        },
        {
            "name": "中文繁体",
            "alias": "cnt",
            "enable": "1",
            "welcome": "333",
            "text1": "444",
            "text2": "555",
            "text3": "666"
        },
        {
            "name": "英语",
            "alias": "eng",
            "enable": "1",
            "welcome": "fdasfads",
            "text1": "fdasfads",
            "text2": "fdsa",
            "text3": "fdsafdsa"
        },
        {
            "name": "日语",
            "alias": "jp",
            "enable": "0",
            "welcome": "fdasgdsag",
            "text1": "sgdsagds",
            "text2": "gdsagdsa",
            "text3": "gasdgdsags"
        },
        {
            "name": "韩语",
            "alias": "kr",
            "enable": "0",
            "welcome": "5fdsa",
            "text1": "gdsa",
            "text2": "gdsa",
            "text3": "hsahsda"
        }
    ],
    "payments": [
        "alipay",
        "weixin"
    ]
}
</pre>


### 2.**天气接口** 

### 3.**酒店商城分类** 
* 接口说明：获取酒店商城分类信息
* 请求地址：*/api/2.0/hotel/category*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/category?token=c733a686306d8c9744631ab498d874b1

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *categories.id* | integer | 分类id |
| *categories.name* | string | 分类中文名 |
| *categories.names* | string | 分类名多语言, 多语言关系参照说明1 |

* 响应范例:
<pre>
{
    "categories": [
        {
            "id": 5,
            "name": "酒水饮料",
            "names": {
                "cns": "酒水饮料",
                "cnt": "酒水饮料2",
                "eng": "酒水饮料3",
                "jp": "",
                "kr": ""
            }
        },
        {
            "id": 6,
            "name": "西餐",
            "names": {
                "cns": "西餐",
                "cnt": "西餐2",
                "eng": "西餐3",
                "jp": "",
                "kr": ""
            }
        }
    ]
}
</pre>

### 4. **酒店商品**
* 接口说明：获取酒店商品信息。
* 请求地址：*/api/2.0/hotel/goods*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)
>* *cid* 选填，获取方法参见 酒店商品分类
>* *page* 选填, 页数
>* *perpage* 选填, 每页记录数默认为18

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/goods?token=c733a686306d8c9744631ab498d874b1&cid=5&perpage=10&page=2

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *total* | integer | 总条数 |
| *perpage* | integer | 分页记录数 |
| *page* | integer | 页数 |
| *pages* | integer | 总页数 |
| *items.id* | integer | 商品id |
| *items.goods_name* | string | 商品名 |
| *items.price* | float | 商品原价 |
| *items.thumburl* | integer | 商品图 |
| *items.description* | string | 商品描述 |
| *items.sales * | string | 销量 |
| *items.names* | string | 多语言的商品名 |


* 响应范例:
<pre>
{
    "total": 2,
    "perpage": 18,
    "page": 1,
    "pages": 1,
    "items": [
        {
            "id": 51,
            "goods_name": "雪碧",
            "category": 5,
            "price": 3,
            "sales": 123,
            "description": "",
            "price_format": "3.00 元",
            "thumburl": "http://iptv4hotel.tos.com/upload/2018/05/12/p5af6a82c4d1d2.jpg",
            "names": {
                "cns": "雪碧",
                "cnt": "雪碧2",
                "eng": "雪碧3",
                "jp": "",
                "kr": ""
            }
        },
        {
            "id": 52,
            "goods_name": "牛排",
            "category": 6,
            "price": 32,
            "sales": "421",
            "description": "",
            "price_format": "32.00 元",
            "thumburl": "http://iptv4hotel.tos.com/upload/2018/05/12/p5af6a9820f240.jpg",
            "names": {
                "cns": "牛排",
                "cnt": "牛排2",
                "eng": "pork",
                "jp": "",
                "kr": ""
            }
        }
    ]
}}
</pre>

### 5.**启动广告**
* 接口说明：无
* 请求地址：*/api/2.0/hotel/apkstartupads*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/apkstartupads?token=c733a686306d8c9744631ab498d874b1

* 响应字段说明:

| 字段 | 类型 | 说明 |      
| :--: | :--:| :-- |
| *id* | integer | 广告id |
| *time* | integer | 广告播放时间 |
| *type* | string | 广告类型 <br> pic 图片广告  <br> video 视频广告 |
| *src* | string | 广告地址 |
* 响应范例:
<pre>
{
    "id": 23,
    "time": 42,
    "type": "pic",
    "src": "http://iptv4hotel.tos.com/upload/2018/05/08/p5af1714bb50a4.jpg"
}
</pre>

### 6.**首页幻灯片**
* 接口说明：无
* 请求地址：*/api/2.0/hotel/indexrotations*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/indexrotations?token=c733a686306d8c9744631ab498d874b1

* 响应字段说明:

| 字段 | 类型 | 说明 |      
| :--: | :--:| :-- |
| *interval* | integer | 首页幻灯片切换时间 |
| *rotation_type* | integer | 首页幻灯片切换模式（仅针对图片模式有效）<br> 1 滑动切换 <br>  2 渐入模式 |
| *items.id* | integer | 幻灯片id |
| *items.type* | string | 幻灯片类型 <br> pic 图片广告  <br> video 视频广告 |
| *items.src* | string | 幻灯片地址 |

* 响应范例:
<pre>
{
    "total": 2,
    "interval": 1,
    "rotation_type": 2,
    "items": [
        {
            "id": 1,
            "type": "pic",
            "src": "http://iptv4hotel.tos.com/upload/2018/05/08/p5af1907286005.jpg"
        },
        {
            "id": 2,
            "type": "video",
            "src": "http://iptv.tos.com/1.mp4"
        }
    ]
}
</pre>


### 7.**集成应用**
* 接口说明：无
* 请求地址：*/api/2.0/hotel/nativeapps*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/nativeapps?token=c733a686306d8c9744631ab498d874b1

* 响应字段说明:

| 字段 | 类型 | 说明 |      
| :--: | :--:| :-- |
| *total* | integer | 总条数 |
| *items.app_package_name* | string | 应用包名称 |
| *items.type* | string | 图标控制 <br> 1 使用应用原生图标和名称  <br> 2 使用自定义图标和名称 |
| *items.src* | string | 应用自定义图标 |
| *items.names* | object | 应用自定义名称, 多语言关系参照说明1  |
| *items.apkurl* | string | apk 地址 |

* 响应范例:
<pre>
{
    "total": 2,
    "items": [
        {
            "app_package_name": "22",
            "type": "2",
            "names": {
                "cns": "fdasg",
                "cnt": "dsagds",
                "eng": "agdsgads",
                "jp": "",
                "kr": ""
            },
            "src": "http://iptv4hotel.tos.com/upload/2018/05/09/p5af2a1eb77c5c.jpg",
            "apkurl": "http://iptv4hotel.tos.com/upload/apk/5afb9f95ad4af.apk"
        },
        {
            "app_package_name": "22",
            "type": "1",
            "names": {
                "cns": "",
                "cnt": "",
                "eng": "",
                "jp": "",
                "kr": ""
            },
            "src": "",
            "apkurl": "http://iptv4hotel.tos.com/upload/apk/5afba064a32a9.apk"
        }
    ]
}
</pre>

### 8.**关于我们**
* 接口说明：无
* 请求地址：*/api/2.0/hotel/aboutus*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/aboutus?token=c733a686306d8c9744631ab498d874b1

* 响应字段说明:

| 字段 | 类型 | 说明 |      
| :--: | :--:| :-- |
| *total* | integer | 总条数 |
| *interval* | integer | 幻灯片切换时间 |
| *items.bgm* | integer | 幻灯片背景音乐 |
| *items.type* | string | 幻灯片类型 <br> pic 图片  <br> video 视频 |
| *items.mode* | string | 幻灯片切换模式控制 <br> 1 滑入  <br> 2 渐入 |
| *items.loop* | string | 视频播放控制模式 <br> 1 只播放一次  <br> 2 循环播放 |
| *items.time* | string | 幻灯片切换时间 |
| *items.video* | string | 幻灯片视频地址 |
| *items.pics* | string | 幻灯片图片地址 |

* 响应范例:
<pre>
{
    "total": 2,
    "interval": 5,
    "items": [
        {
            "bgm": "",
            "loop": "2",
            "mode": "",
            "type": "video",
            "names": {
                "cns": "fdasg",
                "cnt": "dsagdas",
                "eng": "gdsa",
                "jp": "",
                "kr": ""
            },
            "video": "http://iptv4hotel.tos.com/manage#/hotel2/6/1.mp4",
            "pics": [],
            "time": 12
        },
        {
            "bgm": "http://fdasf.gdas.gds.agds.com/gdas/gds/ag/adsg/ads.mp3",
            "loop": "",
            "mode": "1",
            "type": "pic",
            "names": {
                "cns": "3412fda",
                "cnt": "gdas",
                "eng": "gdsagds",
                "jp": "",
                "kr": ""
            },
            "video": "",
            "pics": [
                "http://iptv4hotel.tos.com/upload/2018/05/10/p5af3f3cb193ea.jpg",
                "http://iptv4hotel.tos.com/upload/2018/05/10/p5af3f3d074a33.jpg",
                "http://iptv4hotel.tos.com/upload/2018/05/10/p5af3f3d87d17c.jpg"
            ],
            "time": 12
        }
    ]
}
</pre>

### 9.**周边景点**
* 接口说明：无
* 请求地址：*/api/2.0/hotel/around*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/around?token=c733a686306d8c9744631ab498d874b1

* 响应字段说明:

| 字段 | 类型 | 说明 |      
| :--: | :--:| :-- |
| *total* | integer | 总条数 |
| *interval* | integer | 幻灯片切换时间 |
| *items.src* | string | 图片地址 |

* 响应范例:
<pre>
{
    "total": 2,
    "interval": 5,
    "items": [
        {
            "src": "http://iptv4hotel.tos.com/upload/2018/05/10/p5af430165731e.jpg"
        },
        {
            "src": "http://iptv4hotel.tos.com/upload/2018/05/10/p5af449fe2846b.jpg"
        }
    ]
}
</pre>

### 10.**滚动字幕**
* 接口说明：无
* 请求地址：*/api/2.0/hotel/captionads*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/captionads?token=c733a686306d8c9744631ab498d874b1

* 响应字段说明:

| 字段 | 类型 | 说明 |      
| :--: | :--:| :-- |
| *total* | integer | 总条数 |
| *items* | object | 字幕内容 |

* 响应范例:
<pre>
{
    "total": 2,
    "items": [
        "421",
        "fdasfdasfdsa"
    ]
}
</pre>

### 11.**提交订单接口**
* 接口说明：无
* 请求地址：*/api/2.0/hotel/ordersubmit*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)
>* *goods[]* 商品id和数量, 数组的方式传递多个商品，获取方法参见酒店商品接口 (必填)
>* *payment* 支付方式，获取方法参见酒店设置接口 (必填)

* 请求范例:
http://my.tmos.cn:15280/api/2.0/hotel/ordersubmit?token=c733a686306d8c9744631ab498d874b1&goods[51]=2&goods[52]=3&payment=weixin

* 响应字段说明:

| 字段 | 类型 | 说明 |      
| :--: | :--:| :-- |
| *code* | integer | 状态码 |
| *msg* | string | 消息 |
| *order_sn* | string | 订单号 |

* 响应范例:
<pre>
{
    "code": 0,
    "msg": "成功",
    "order_sn": "201805160806108913"
}
</pre>


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

##### 2. 酒店版状态码
| 状态码 |  说明 |	  
| :--: | :-- |
| *200* | 商品未上架或者商品不存在 |
| *201* | 商品数量不对 |
| *202* | 订单不存在 |
| *203* | 分类id不属于当前用户分组 |

### 说明
##### 1. 多语言对应关系
| 语言标识 | 语言 |	  
| :--: | :-- |
| *cns* | 中文简体|
| *cnt* | 中文繁体|
| *eng* | 英文|
| *jp* | 日语|
| *kr* | 韩语|
