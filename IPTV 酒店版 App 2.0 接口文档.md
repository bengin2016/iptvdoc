# IPTV 酒店版 App 2.0 接口文档

> 测试服务器 http://my.tmos.cn:15180/

### 1.**首页相关资源**
* 接口说明：获取首页相关资源。
* 请求地址：*/api/app/hotel/index*
* 请求方式：*GET*
* 参数:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *title* | bool | 标题 |
| *home_rotation_time* | integer | 首页轮播图片切换时间 |
| *text1* | string | 扩展显示1 |
| *text2* | string | 扩展显示2 |
| *text3* | string | 扩展显示3 |
| *text4* | string | 扩展显示4 |
| *captionads*   | array | 首页幻灯片图片 |
| *rotations*   | array | 首页滚动字幕 |

### 2.**关于我们**
* 接口说明：获取关于我们相关资源。
* 请求地址：*/api/app/hotel/aboutus*
* 请求方式：*GET*
* 参数:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *rotationinterval* | integer | 关于我们轮播图片切换时间 |
| *rotations*   | array | 关于我们轮播图片 |
| *rotations.index*   | string | 关于我们轮播图片的顺序 |
| *rotations.src*   | string | 关于我们轮播图片的地址 |

### 3.**客房分类**
* 接口说明：获取客房分类。
* 请求地址：*/api/app/hotel/category/kefang*
* 请求方式：*GET*
* 参数:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *categories.id* | integer | 分类id |
| *categories.name* | string | 客房分类名 |

### 4.**酒水分类**
* 接口说明：获取酒水分类。
* 请求地址：*/api/app/hotel/category/jiushui*
* 请求方式：*GET*
* 参数:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *categories.id* | integer | 分类id |
| *categories.name* | string | 酒水分类名 |

### 5.**获取商品**
* 接口说明：通过分类id获取商品。
* 请求地址：*/api/app/hotel/goods*
* 请求方式：*GET*
* 参数:
>* *page* 页数
>* *perpage* 每页记录数
>* *cid* 商品分类id(必填)

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
| *items.vipprice* | float | 商品vip价格 |
| *items.thumburl* | integer | 商品图 |
| *items.description* | string | 商品描述 |

### 6.**提交订单**
* 接口说明：-
* 请求地址：*/api/hotel/ordersubmit*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)
>* *goods[]* 商品id => 商品数量 例如：goods[1] =2&goods[3]=4

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | integer | 状态码 |
| *msg* | string | 消息 |

### 7.**app首页按钮**
* 接口说明：-
* 请求地址：*/api/app/hotel/appbtns*
* 请求方式：*GET*
* 参数:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *title* | string | 按钮文字 |
| *package* | string | 入口点 |

### 8.**播放前视频**
* 接口说明：-
* 请求地址：*/api/app/hotel/adsbeforeplay*
* 请求方式：*GET*
* 参数:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *item.url* | string | 视频地址 |
| *item.countdown* | integer | 播放倒计时 |
| *total* | integer | 播放前视频总数 |

### 9.**魅力山东幻灯片图片**
* 接口说明：获取魅力山东幻灯片图片相关资源。
* 请求地址：*/api/app/hotel/mlsd*
* 请求方式：*GET*
* 参数:
>* 无

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *rotationinterval* | integer | 魅力山东幻灯片图片切换时间 |
| *rotations*   | array | 魅力山东幻灯片图片 |
| *rotations.index*   | string | 魅力山东幻灯片图片的顺序 |
| *rotations.src*   | string | 魅力山东幻灯片图片的地址 |

### 10.**客房服务1**
* 接口说明：获取客房服务相关资源。
* 请求地址：*/api/app/hotel/gethotelservice1*
* 请求方式：*GET*
* 参数:
>* 无 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *count* | integer | 状态码 |
| *services.id*   | string | 服务id |
| *services.title*   | string | 名称 |
| *services.name*   | string | 名称 |
| *services.content*   | string | 返回文字 |

### 11.**客房服务2**
* 接口说明：获取客房服务2相关资源。
* 请求地址：*/api/app/hotel/gethotelservice2*
* 请求方式：*GET*
* 参数:
>* 无 

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *count* | integer | 状态码 |
| *services.id*   | string | 服务id |
| *services.action*   | string | 按钮执行动作 1 打开第三方应用 2 点击返回文字 |
| *services.name*   | string | 名称 |
| *services.thumburl*   | string | 图标 |
| *services.text*   | string | 返回文字 |
| *services.package*   | string | 入口点 |


### 12.**提交服务订单**
* 接口说明：-
* 请求地址：*/api/hotel/servicesubmit*
* 请求方式：*GET*
* 参数:
>* *token* 令牌，获取方法参见用户登录 (必填)
>* *services[0]* 索引 => 服务id 例如：services[0]=2&services[1]=4

* 响应字段说明:

| 字段 | 类型 | 说明 |	  
| :--: | :--:| :-- |
| *code* | integer | 状态码 |
| *msg* | string | 消息 |
        
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
| *303* | 按钮别名不正确 |
| *304* | 按钮描述为空 |


        
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