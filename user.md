# 用户信息
## 1.用户打印服务

|  接口  | 说明 |
|------ |----- |
|[prints/user/upfile](#upfile)| 上传文件 |
|[prints/user/fileinfo](#fileinfo)| 指定文件信息 |
|[prints/shop/getshopnearby](#getshopnearby)| 获得附近商户信息|
|[prints/user/printorder](#printorder)| 用户打印订单列表|

|[prints/user/printorder](#printorder)| 用户打印订单列表|



***
## 错误码列表
|  错误码  | 说明 |
|------ |----- |
|   0   | 正确 |
|   1   | 错误 |
|   2   | 参数错误|

***


## 接口详情

---

* <span id = "upfile">上传文件</span>

    * 请求地址:https://api.szsxsoft.com/api/prints/user/upfile
    * 接口备注:上传文件
    * 请求参数说明:
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|
    |file |string|true|文件|
    |file_title |string|true|文件名(可空)|
    
    * JSON返回值
                
            {
                code: 0
                data: "/data/9/201909070903005d7301c4bda88.jpg"
                msg: "success"
            }

---

* <span id = "fileinfo">获得指定文件</span>

    * 请求地址:https://api.szsxsoft.com/api/prints/user/fileinfo
    * 接口备注:获得指定文件
    * 请求参数说明:
    
    | 名称 | 类型 | 必填 |说明|
    |----- |------| ---- |----|
    |user_id |int|true|用户id |
    |file_id |int|true|文件id |
    
    * JSON返回值
                
            {
            	"code": 0,
            	"msg": "success",
            	"data": {
            		"file_id": 95, //文件id
            		"file_title": "个人工资收入证明.doc", //文件名
            		"file_url": "http:\/\/file.szsxsoft.com\/data\/9\/201909282318045d8f79ac6e2c7.doc", //原始地址
            		"file_size": 20480,
            		"file_type": "doc",
            		"pdf_url": "http:\/\/file.szsxsoft.com\/data\/9\/201909282318045d8f79ac6e2c7.pdf", //打印地址
            		"pdf_page": 1,
            		"print_paper": 2,
            		"print_color": 1,
            		"print_num": 2
            	}
            }

---


* <span id = "getshopnearby">获得附近商户信息</span>

    * 请求示例：https://api.szsxsoft.com/api/prints/shop/getshopnearby
    * 接口备注：获取附近商户
    * 请求参数说明：
    
        | 名称 | 类型 | 必填 |说明|
        |----- |------| ---- |----|
        |user_id |string|true|用户id(可不用)|
        |page |string|true|1|
        |size |string|true|5|
        |latitude |string|true|自己纬度|
        |longitude | string |true|自己经度|

    * JSON返回示例：
  
            {
                "code": 0,
                "msg": "success",
                "data": "未写"
            }
---


* <span id = "printorder">用户提交打印订单</span>

    * 请求示例：https://api.szsxsoft.com/api/prints/user/printorder
    * 接口备注：获取附近商户
    * 请求参数说明：
    
        | 名称 | 类型 | 必填 |说明|
        |----- |------| ---- |----|
        |shop_id |string|true|商户id|
        |user_id | string |true|用户id|
        |file_id | string |true|文件id|

    * JSON返回示例：
  
            {
                "code": 0,
                "msg": "success",
                "data": "订单创建成功"
            }
---




