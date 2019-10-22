# 商户信息
## 1.一些接口目录

|  接口  | 说明 |
|------ |----- |
|[prints/shop/regshop](#regshop)| 简单注册商户|
|[prints/shop/addshop](#addshop)| 添加商户|
|[prints/shop/getshop](#getshop)| 获取商户基本信息|
|[prints/shop/getshopreg](#getshopreg)| 获取商家注册时信息|
|[prints/shop/shoplogin](#shoplogin)| 商户登录|
|[prints/shop/updateshop](#updateshop)| 编辑商户信息|
|[prints/printer/addprint](#addprint)| 添加打印机|
|[prints/printer/printorder](#printorder)| 商家获取打印订单列表|
|[prints/shop/printstatus](#printstatus)| 更改打印状态 |
|[prints/shop/orderstatus](#printorder)| 更改订单状态 |
|[prints/shop/addblack](#addblack)| 用户加入黑名单 |
|[prints/shop/delblack](#delblack)| 用户移除黑名单 |
|[prints/shop/getblack](#getblack)| 查询一个用户是否在黑名单 |
|[prints/shop/blacklist](#blacklist)| 黑名单列表 |

***
##错误码列表

|  错误码  | 说明 |
|------ |----- |
|   0   | 正确 |
|   1   | 错误 |
|   2   | 参数错误|

***
    * 返回格式：Json
    * 请求方式：Post


## 接口详情


* <span id = "regshop">简单注册商户</span>
    * 请求示例：https://api.szsxsoft.com/api/prints/shop/regshop
    * 接口备注：提交信息,简单注册商户
    * 请求参数说明：
    
        | 名称 | 类型 | 必填 |说明|
        |----- |------| ---- |----|
        |username |string|true|商户用户名|
        |password | string |true|商户登录密码|
        |shopname | string |false|商户名称(可选)|
        |latitude | string |false|经度(可选)|
        |longitude | string |false|纬度(可选)|

    * JSON返回示例：
  
            {
                "code": 0,
                "msg": "success",
                "data": "注册成功"
            }
---

* <span id = "addshop">添加商户</span>
    * 请求示例：https://api.szsxsoft.com/api/prints/shop/addshop
    * 接口备注：提交信息,添加商户的基本信息
    * 请求参数说明：
    
        | 名称 | 类型 | 必填 |说明|
        |----- |------| ---- |----|
        |username |string|true|商户用户名|
        |password | string |true|商户登录密码|
        |shopname | string |true|商户名称|
        |shopimgurl | string |false|商户头像(暂时没有)|
        |address | string |true|地址(可讨论加province,city,district)|
        |A4_black | string |true|A4单黑价格|
        |A4_colour | string |true|A4彩色价格|
        |A3_black | string |true|A3单黑价格|
        |A3_colour | string |true|A3彩色价格|
        |phone | string |true|负责人手机号|
        |start_week | string |true|开始营业周期|
        |end_week | string |true|结束营业周期|
        |start_time | string |true|开始营业时间|
        |end_time | string |true|结束营业时间|
        |reg_name | string |true|申请人姓名|
        |reg_phone | string |true|申请人手机|

    * 返回参数说明：
    
        | 名称 | 类型 |说明|
        |----- |------|----|
        | code | int|状态码|
        | msg | string|请求信息|
        | data | json|返回数据|

    * JSON返回示例：
  
            {
                "code": 0,
                "msg": "success",
                "data": "入驻成功"
            }
---

* <span id = "getshop">获取商户信息</span>
    * 请求示例：https://api.szsxsoft.com/api/prints/shop/getshop
    * 接口备注：获取商户基本信息.
    * 请求参数说明：

        | 名称 | 类型 | 必填 |说明|
        |----- |------| ---- |----|
        |ship_id |string|true|商户id|

    * 返回参数说明：
    
        | 名称 | 类型 |说明|
        |----- |------|----|
        | code | int|状态码|
        | msg | string|请求信息|
        | data | json|返回数据|

    * JSON返回示例：

            {
                "code": 0,
                "msg": "success",
                "data": {
                    "shop_id": 1,
                    "username": "szsxsoft",
                    "shopname": "苏州书香科技公司",
                    "shopimgurl": "http:\/\/api.szsxsoft.com\/uploads\/images\/shop\/shop.png",
                    "phone": "15226585985",
                    "business_hours_id": 1,
                    "address": "江苏省苏州市姑苏区公安分局",
                    "is_vip": 0,
                    "vip_time": 0,
                    "reg_name": "店长小王",
                    "reg_phone": "15265698569",
                    "create_time": "2019-08-14",
                    "bus_day": "周一~周五", //营业日期
                    "bus_time": "09:00~18:00", //营业时间
                    "price": { //价格
                        "A4_black": "8.00",
                        "A4_colour": "9.00",
                        "A3_black": "10.00",
                        "A3_colour": "11.00"
                    }
                }
            }
> 请求例子: https://api.szsxsoft.com/api/prints/shop/getshop?shop_id=1
---

* <span id="getshopreg">获取商家注册时信息</span>
 
    * 接口地址 : https://api.szsxsoft.com/api/prints/shop/getshopreg

    * 接口备注：获取商家注册时信息.
    
    * 请求参数说明：
    
        | 名称 | 类型 | 必填 |说明|
        |----- |------| ---- |----|
        |ship_id |string|true|商户id|

    * 返回参数说明：
    
        | 名称 | 类型 |说明|
        |----- |------|----|
        | code | int|状态码|
        | msg | string|请求信息|
        | data | json|返回数据|
        
    * JSON返回示例：
    
            {
                "code": 0,
                "msg": "success",
                "data": {
                    "shop_id": 1,
                    "username": "szsxsofr",
                    "shopname": "苏州书香科技公司",
                    "shopimgurl": "",
                    "phone": "15226585985",
                    "address": "江苏省搜州市姑苏区",
                    "is_vip": 0,
                    "vip_time": 0,
                    "reg_name": "店长小王",
                    "reg_phone": "15265698569",
                    "create_time": "2019-08-14",
                    "business_hours_id": 1,
                    "start_week": "周一",
                    "end_week": "周五",
                    "start_time": "09:00",
                    "end_time": "18:00",
                    "A4_black": "1.00",
                    "A4_colour": "2.00",
                    "A3_black": "1.00",
                    "A3_colour": "4.00"
                }
            }          

---
* <span id="shoplogin">商户登录</span>
    * 请求示例：https://api.szsxsoft.com/api/prints/shop/shoplogin
    * 接口备注：商户登录.
    * 请求参数说明：
    
        | 名称 | 类型 | 必填 |说明|
        |----- |------| ---- |----|
        |username |string|true|商户用户名|
        |password |string|true|商户密码|

    * 返回参数说明：
    
        | 名称 | 类型 |说明|
        |----- |------|----|
        | code | int|状态码|
        | msg | string|请求信息|
        | data | json|返回数据|

    * JSON返回示例：

            {
                "code": 0,
                "msg": "success",
                "data": {
                    "shop_id": 4,
                    "username": "123456",
                    "shopname": "水箱可以",
                    "shopimgurl": "",
                    "phone": "15225185985",
                    "address": "江苏州市姑苏区",
                    "is_vip": 0,
                    "vip_time": 0,
                    "reg_name": "店长小",
                    "reg_phone": "15265698569",
                    "create_time": 1565799647,
                    "token": "rVgqthwZ9jsnYeZi1g5pWl01F5w",
                    "expire_time": 1568391676
                }
            }
            
---
* <span id = "updateshop">编辑商户信息</span>

     * 请求示例：https://api.szsxsoft.com/api/prints/shop/updateshop
    
    * 接口备注：编辑商户信息.
    
    * 请求参数说明：
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|
    |ship_id |string|true|商户id|
    |username |string|false|用户名(不改)|
    |password |string|true|商户密码|
    |shopname | string |true|商户名称|
    |shopimgurl | string |false|商户头像(暂时没有)|
    |address | string |true|地址(可讨论加province,city,district)|
    |A4_black | string |true|A4单黑价格|
    |A4_colour | string |true|A4彩色价格|
    |A3_black | string |true|A3单黑价格|
    |A3_colour | string |true|A3彩色价格|
    |phone | string |true|负责人手机号|
    |start_week | string |true|开始营业周期|
    |end_week | string |true|结束营业周期|
    |start_time | string |true|开始营业时间|
    |end_time | string |true|结束营业时间|
    |reg_name | string |true|申请人姓名|
    |reg_phone | string |true|申请人手机|

    * 返回参数说明：
    
    | 名称 | 类型 |说明|
    |----- |------|----|
    | code | int|状态码|
    | msg | string|请求信息|
    | data | json|返回数据|
        
    * JSON返回示例：

            {"code":1,"msg":"error","data":"更新失败"}

---

* <span id = "addprint">添加打印机</span>
    * 请求示例：https://api.szsxsoft.com/api/prints/printer/addprint
    
    * 接口备注：添加打印机.
    
    * 请求参数说明：
    

---

* <span id = "printorder">获取订单列表</span>

    * 请求地址:https://api.szsxsoft.com/api/prints/shop/printorder
    * 接口备注:获取订单列表
    * 请求参数说明:
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|
    |shop_id |string|ture|商家id|
    |keywords |string|false| 可查 订单号,取件码(可不传)|
    |order_id |int|1| 订单id(如果传,表示查大于order_id的所有记录)||  
    |print_status |int|1| 打印状态(可不传)||
    |order_status |int|1| 订单状态(可不传)||
    |page |string|1| 当前页(可不传)||
    |size |string|5| 当前页数据量(可不传)||
    
    * JSON返回值 (有些分页字段可能用不上请忽略)
                
            {
            	"code": 0,
            	"msg": "success",
            	"data": [{ //数据,如果页数故意写很大,返回为空
                    "order_id": 4, //订单id
                    "order_sn": "201909307730330974",//订单号
                    "uid": 9, //用户id
                    "shop_id": 1, //商户id
                    "paper_id": 2, //纸质id
                    "printer_paper": "A4",//纸质类型
                    "color_id": 1,//颜色id
                    "printer_color": "单黑",//颜色类型
                    "price": 8,//每张单价
                    "num": 2,//打印分数
                    "count_price": 16,//打印总价格(单价*文件页数*分数)
                    "file_id": 95,//文件id
                    "file_title": "",//文件名
                    "pdf_url": "http:\/\/file.szsxsoft.com\/data\/9\/201909282318045d8f79ac6e2c7.pdf",//打印文件地址
                    "file_page": 1,//文件的页数
                    "file_type": "pdf",//文件类型
                    "file_type_ico": "XXX.png",//真实上传的文件后缀及图标
                    "print_status": 1,//打印状态
                    "order_status": 1,//订单状态
                    "add_time": "1970-01-01 08:00:00",//提交时间
                    "print_time": "",//打印时间
                    "pickup_code": "", //取件码
                    "user": {
                        "uid": 12,
                        "avatar": "https:\/\/wx.qlogo.cn\/mmopen\/vi_32\/VxZg0q2ic9BUYiaRZFfXmYHLSCwOInM4yaExKqCJgy9ylxP2KLd6cAJc1cwjqF2EjoGxmjPWNhZUSfsmibfsVHSJg\/132",
                        "is_vip": 0,
                        "mini_openid": "opqua5fY-iizN3n67ytnEA",
                        "nick_name": "李涛",
                        "phone": "",
                        "sex": 2,
                        "user_name": "",
                        "unionid": "",
                        "vip_time": "1970-01-01"
                    },
                    "shop": {
                        "shop_id": 1,
                        "username": "szsxsoft",
                        "shopname": "苏州书香科技公司",
                        "shopimgurl": "http:\/\/api.szsxsoft.com\/uploads\/images\/shop\/shop.png",
                        "phone": "15226585985",
                        "address": "江苏省苏州市姑苏区公安分局",
                        "reg_name": "店长小王",
                        "is_vip": 0,
                        "vip_time": 0,
                        "reg_phone": "15265698569",
                        "create_time": "2019-08-14"
                    }
                
                 }]
            }
            
> 请求例子:http://api.szsxsoft.com/api/prints/shop/printorder?shop_id=1&print_status=1
        
> 打印状态: 0打印失败,1待打印,2打印完成
> 订单状态: 0未确认,1已确认,2未取件,3.已取件,4.取消订单
---

* <span id = "printstatus">更改打印状态</span>

     * 请求示例：https://api.szsxsoft.com/api/prints/shop/printstatus
    
    * 接口备注：更改打印状态.
    
    * 请求参数说明：
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|
    |shop_id |string|true|商户id|
    |order_sn |string|true|订单号|
    |print_status |string|true|打印状态|
        
    * JSON返回示例：

            {"code":1,"msg":"error","data":"更新失败"}

> 请求例子: https://api.szsxsoft.com/api/prints/shop/printstatus?shop_id=1&order_sn=201910019069990675&print_status=2

> 打印状态号:可以参考订单列表备注
---


* <span id = "orderstatus">更改订单状态</span>

     * 请求示例：https://api.szsxsoft.com/api/prints/shop/orderstatus
    
    * 接口备注：更改订单状态.
    
    * 请求参数说明：
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|
    |ship_id |string|true|商户id|
    |order_sn |string|true|订单号|
    |order_status |string|true|订单状态|
        
    * JSON返回示例：

            {"code":1,"msg":"error","data":"更新失败"}

> 请求例子: https://api.szsxsoft.com/api/prints/shop/orderstatus?shop_id=1&order_sn=201910019069990675&order_status=2

> 订单状态号:可以参考订单列表备注
---

 * <span id = "addblack">添加黑名单</span>

     * 请求示例：https://api.szsxsoft.com/api/prints/shop/addblack
    
    * 接口备注：添加黑名单.
    
    * 请求参数说明：
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|
    |user_id |string|true|用户id|
    |ship_id |string|true|商户id|
        
    * JSON返回示例：

            {"code":1,"msg":"error","data":"添加成功"}
> 
---   

 * <span id = "delblack">移除黑名单</span>

     * 请求示例：https://api.szsxsoft.com/api/prints/shop/delblack
    
    * 接口备注：移除黑名单.
    
    * 请求参数说明：
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|
    |user_id |string|true|用户id|
    |ship_id |string|true|商户id|
        
    * JSON返回示例：

            {"code":1,"msg":"error","data":"移除成功"}
--- 


 * <span id = "getblack">获得一个黑名单用户</span>

     * 请求示例：https://api.szsxsoft.com/api/prints/shop/getblack
    
    * 接口备注：移除黑名单.
    
    * 请求参数说明：
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|
    |user_id |string|true|用户id|
    |ship_id |string|true|商户id|
        
    * JSON返回示例：

            {
            	"code": 0,
            	"msg": "success",
            	"data": {
            		"user_id": 9,
            		"nick_name": "李文涛",
            		"sex": "男",
            		"phone": null,
            		"shop_id": 1, //那个商家添加的
            		"add_time": "2019-10-01 04:48:12"
            	}
            }
> data 为空:则表示不在黑名单列表
--- 

 * <span id = "blacklist">黑名单列表</span>

     * 请求示例：https://api.szsxsoft.com/api/prints/shop/blacklist
    
    * 接口备注：黑名单列表.
    
    * 请求参数说明：
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|

    * JSON返回示例：
    

> 未写
--- 





