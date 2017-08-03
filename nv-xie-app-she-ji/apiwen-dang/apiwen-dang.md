# 数据API接口文档 {#数据api接口文档}

#### response格式

```
{
    success:true/false,
    message:'如失败，需要给出原因',
    data:数据对象
}
```

##### apibody统一为json格式的字符串

## 1.登陆

访问路径URL:  [http://192.168.127.1:8080/api/login](http://192.168.127.1:8080/api/login)

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| name | 登陆用户名 |
| :--- | :--- |
| pwd | 登陆密码 |

返回值：

```
{
    success:true,
    data:{
        uid:1001,
        token:xxxx
    }
}

```

### 2，获取商品 {#2，获取商品}

请求地址：[http://host:port/api/getProduct](http://host:port/api/getProduct)s

请求方式：GET

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |
| type | 0为全部商品，1为新品，默认为0 |

返回值：

```
{
    success:true,
    data:[
        Product对象,
        ...
    ]
}

```

### 3，提交预定信息 {#3，提交预定信息}

请求地址：[http://host:port/api/postPreOrider](http://host:port/api/postPreOrider)

请求方式：POST

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |
| productID | 商品ID |
| count | 预定数量 |

返回值：

```
{
    success:true,
}

```

### 4，获取预定记录 {#4，获取预定记录}

请求地址：[http://host:port/api/getPerOrders](http://host:port/api/getPerOrders)

请求方式：GET

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |

返回值：

```
{
    success:true,
    data:[
        PreOrder对象,
        ...
    ]
}

```

### 5，获取订单列表 {#5，获取订单列表}

请求地址：[http://host:port/api/getOrders](http://host:port/api/getOrders)

请求方式：GET

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |

返回值：

```
{
    success:true,
    data:[
        Order对象，
        ...
    ]
}

```

### 6，获取订单明细 {#6，获取订单明细}

请求地址：[http://host:port/api/getOrderDetails](http://host:port/api/getOrderDetails)

请求方式：GET

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |
| orderID | 订单ID |

返回值：

```
{
    success:true,
    data:[
        OrderDetail对象，
        ...
    ]
}

```

### 7,确认订单 {#7确认订单}

请求地址：[http://host:port/api/confirmOrder](http://host:port/api/confirmOrder)

请求方式：POST

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |
| orderID | 确认订单ID |

返回值：

```
{
    success:true,
}

```

### 8，退货 {#8，退货}

请求地址：[http://host:port/api/backProduct](http://host:port/api/backProduct)

请求方式：POST

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |
| orderID | 订单ID |
| orderDetailID | 订单明细ID |
| count | 退货数量 |

返回值：

```
{
    success:true,
}

```

### 9,换货 {#9换货}

请求地址：[http://host:port/api/changeProduct](http://host:port/api/changeProduct)

请求方式：POST

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |
| orderID | 订单ID |
| orderDetailID | 订单明细ID |
| count | 换货数量 |
| colorID | 换货颜色ID |
| sizeID | 换货尺码ID |

返回值：

```
{
    success:true,
}

```

### 10，获取账单明细 {#10，获取账单明细}

请求地址：[http://host:port/api/getBillDetails](http://host:port/api/getBillDetails)

请求方式：GET

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |

返回值：

```
{
    success:true,
    data:[
        账单明细对象,
        ...
    ]
}

```

### 11，获取对账单 {#11，获取对账单}

请求地址：[http://host:port/api/getBill](http://host:port/api/getBill)

请求方式：GET

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |

返回值：

```
{
    success:true,
    data:对账单对象,
}

```

### 12，确认对账单 {#12，确认对账单}

请求地址：[http://host:port/api/confirmBill](http://host:port/api/confirmBill)

请求方式：POST

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |
| billID | 对账单ID |

返回值：

```
{
    success:true,
}

```

### 13，获取历史对账单 {#13，获取历史对账单}

请求地址：[http://host:port/api/getHistoryBills](http://host:port/api/getHistoryBills)

请求方式：GET

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |

返回值：

```
{
    success:true,
    data:[
        对账单对象，
        ...
    ],
}

```

### 14,获取通知 {#14获取通知}

请求地址：[http://host:port/api/getNotices](http://host:port/api/getNotices)

请求方式：GET

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |

返回值：

```
{
    success:true,
    data:[
        通知对象，
        ...
    ],
}

```

### 15，修改密码 {#15，修改密码}

请求地址：[http://host:port/api/user/setPassword](http://host:port/api/user/setPassword)

请求方式：POST

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| token | 登录令牌 |
| currentpwd | 当前密码 |
| newpwd | 新密码 |

返回

```
{
    success:true,
}
```



