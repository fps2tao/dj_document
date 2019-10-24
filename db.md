# 我的单据及打印数据库说明
### 一.商家部分

##### 1.商家数据库 (printer_shop)

字段名 | 字段类型 | 字段描述
--- | --- | ---
id | int | 自增id
username | String | 用户名
password | String | 密码
shopname | String | 店铺名称
tel | String | 用户名
phone |String|打印机负责人
business_hours_id | int | 营业时间(外键)
wx_province | String |微信地图接口省
wx_city | String |微信地图接口城市
wx_district | String |微信地图接口区
wx_address | String |微信地图接口详细地址
address | String | 详细地址(全地址)
latitude | int | 纬度
longitude | int | 经度
shopimgurl | String | 商家图片
is_vip | int | 是否vip
vip_time | int | vip过期时间
reg_name | String | 申请人姓名
reg_phone | String | 申请人手机
create_time | int | 创建时间


##### 2.商家营业时间 (business_hours)
字段名 | 字段类型 | 字段描述
--- | --- | ---
id | int | 自增id
start_week|String|开始星期
end_week|String|结束星期
start_time|String|开始时间
end_time|String|结束时间


##### 3.打印机颜色 (printer_color)
字段名 | 字段类型 | 字段描述
--- | --- | ---
id | int | 自增id
name | String | 颜色(单黑,彩色)
> 只有两个值 1.单黑 2.彩色

##### 4.打印机纸张 (printer_paper)
字段名 | 字段类型 | 字段描述
--- | --- | ---
id | int | 自增id
name | String | 纸张(A3,A4)
> 只有两个值 1.A3 2.A4

##### 5.商家打印价格 (printer_price)
字段名 | 字段类型 | 字段描述
--- | --- | ---
id | int | 自增id
shop_id | int | 商家id
printer_id | int | 打印机id(暂不用,价格跟店走)
type | int | 11:A3单黑,12:A3彩色,21:A4单黑,22:A4彩色
paper_id | int | 纸质id
color_id | int | 颜色id
price | decimal | 价格
> type类型,第一个代表paper_id,第二个代表color_id


##### 6.商家打印机 (printer)
字段名 | 字段类型 | 字段描述
--- | --- | ---
id | int | 自增id
shop_id | int | 商家id
printer_no | varchar | 打印机编号
paper_id | varchar | 支持纸张
color_id | varchar | 支持颜色
brand | varchar | 品牌
state | tinyint | 状态

##### 7.用户文件表 (printer_file)
字段名 | 字段类型 | 字段描述
--- | --- | ---
id | int | 自增id
file_title | int | 文件名
uid | int | 用户id
file_url | varchar | 原文件路径
file_size | double |原文件大小
file_type | varchar | 原文件类型
pdf_url | varchar | 打印文件路径
pdf_page | int | 打印文件页数
print_paper | tinyint | 打印纸张
print_color | tinyint | 打印颜色
print_num | int | 打印份数
add_time | int | 上传时间
is_del | tinyint | 是否删除
status | tinyint | 0处理中1处理成功2处理失败
> 程序会统一,把上传的文件转化成pdf进行打印

##### 8.打印订单表 (print_order)
字段名 | 字段类型 | 字段描述
--- | --- | ---
order_id | int | 自增id
order_sn | int | 订单编号
uid | varchar | 用户id
shop_id | varchar | 商户id
printer_id | varchar | 打印机id
printer_no | varchar | 打印机编号
paper_id | tinyint | 打印纸质id
printer_paper | tinyint | 打印纸质
color_id | tinyint | 打印颜色id
printer_color | tinyint | 打印颜色
price | tinyint | 单价
num | tinyint | 打印份数
count_price | tinyint | 打印总价
file_id | tinyint | 打印文件id
pdf_url | varchar | 打印url
file_page | int | 打印文件页数
original_file_type| varchar | 原始文件类型
file_type| varchar | 打印文件类型(pdf)
print_status | tinyint | 打印状态 0打印失败,1待打印,2打印完成
order_status | tinyint | 0未确认,1已确认,2未取件,3.已取件,4.取消订单
add_time | tinyint | 订单生成时间
print_time | tinyint | 打印时间
pickup_code |varchar | 取件码
is_del| tinyint | 是否删除 1正常,0删除了
> 没有支付金额和支付时间,因为支付让商户和用户自行处理


##### 9.黑名单表 (blackusers)
字段名 | 字段类型 | 字段描述
--- | --- | ---
id | int | 自增id
user_id | int | 黑名单用户id
shop_id | int | 那个商家添加的
add_time | int | 添加时间


















