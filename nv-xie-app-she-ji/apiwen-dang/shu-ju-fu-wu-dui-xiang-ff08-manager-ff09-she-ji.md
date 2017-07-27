# 设计数据服务对象

依照元数据设计，我们设计6个数据服务对象

* UserManager
* ProductManager
* PreOrderManager
* OrderManager       
* BillManager            
* NoticeManager         

---

#### **UserManager**

##### //登陆功能

login\(user,loginResltCallBack\);

参数说明：

```
//输入参数，登陆所需数据，为一个对象
user
{
    name:'xxx',
    pwd:'xxxx',
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :--- | :--- |
| name | 用户输入的用户名 |  |
| pwd | 用户输入的密码 |  |

```
loginResltCallBack,登录完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //修改密码功能

setPwd\(parameter,setPwdResultCallBack\);

参数说明：

```
//输入参数，修改密码所需数据，为一个对象
parameter
{
    currentpwd:'xxxx',
    newpwd:'xxxxx',
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :--- | :--- |
| currentpwd | 当前密码 |  |
| newpwd | 新密码 |  |

```
setPwdResltCallBack,修改密码完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

---

#### ProductManager

##### //获取商品

getProducts\(CallBack\);

无输入参数：

```
CallBack,获取商品完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //提交预定信息

postPreOrder\(parameter,recultCallBack\);

参数说明：

```
//输入参数，提交预定信息所需数据，为一个对象
parameter
{
    productID:'xxxx',
    count:'xxxxx',
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :--- | :--- |
| productID | 商品ID |  |
| count | 预定数量 |  |

```
recultCallBack,提交预定信息完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

---

#### PerOrderManager

##### //获取预定记录

getPerOrders\(recultCallBack\);

无输入参数

```
recultCallBack,获取预定记录完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

---

#### OrderManager

##### //获取订单信息

getOrders\(resultCallBack\);

无输入参数：

```
recultCallBack,获取订单信息完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //获取订单明细

getOrderDetails\(orderID,resultCallBack\);

参数说明：

```
//输入参数，获取订单明细所需数据

    orderID:12,
```

#### 字段说明

```
recultCallBack,获取订单明细完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //确认订单

confirmOrder\(orderID,recultCallBack\);

参数说明：

```
//输入参数，确认订单所需数据
    orderID:12,
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :--- | :--- |
| orderID | 确认订单ID |  |

```
recultCallBack,确认订单完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //退货

backProduct\(parameter,resultCallBack\);

参数说明：

```
//输入参数，退货所需数据，为一个对象
parameter
{
    orderID:12,
    orderDetailID:12,
    count:11,
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :--- | :--- |
| orderID | 订单ID |  |
| orderDetailID | 订单详情ID |  |
| count | 退货数量 |  |

```
recultCallBack,退货完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //换货

changeProduct\(parameter,resultCallBack\);

参数说明：

```
//输入参数，换货所需数据，为一个对象
parameter
{
    orderID:12,
    orderDetailID:12,
    count:11,
    colorID:1,
    sizeID:1,
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :--- | :--- |
| orderID | 订单ID |  |
| orderDetailID | 订单详情ID |  |
| count | 换货数量 |  |
| colorID | 换货颜色ID |  |
| sizeID | 换货尺码ID |  |

```
recultCallBack,换货完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

---

#### BillManager

##### //获取账单明细

getBillDetails\(resultCallBack\);

无输入参数

```
recultCallBack,获取账单明细完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //获取对账单

getBill\(resultCallBack\);

无输入参数

```
recultCallBack,获取对账单完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //确认对账单

confirmBill\(billID,resultCallBack\)；

参数说明：

```
//输入参数，认对账单所需数据
    billID:12,
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :--- | :--- |
| billID | 对订单ID |  |

```
recultCallBack,确认对账单完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //获取历史对账单

getHistoryBills\(resultCallBack\);

无输入参数

```
recultCallBack,获取历史对账单完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

---

#### NoticeManager

##### //获取通知

getNotices\(resultCallBack\);

无输入参数

```
recultCallBack,获取通知完成事件回调函数。

(result,message)=>void

result：登录结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

---



