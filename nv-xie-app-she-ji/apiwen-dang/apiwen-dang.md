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
//当success为true时
{
    success:true,
    data:{
        RealName:'真正名字',
        token:'登录令牌',
        },
}
//当success为false时
{
    success:false,
    message:'错误详情',
}
```

## 2.获取全部产品信息

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)shop

请求方式：GET

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    token:'登录令牌',
}
```

请求参数：无

返回值：

```
{
    success:true,
    data:[
      {
        ID:1,
        ShopNumber:'123456',
        Name:'xxxx',
        Price:12,
        Season:'夏季',
        Color:[白色,黑色,灰色],
        Style:'潮流',
        Brand:'哈根达斯',
        Size:[36,37,38,39,40,41],
      },
      ...
    ]
}
```

## 3.获取订购数据

访问路径URL:  [http://192.168.127.1:8080/api/Reserve](http://192.168.127.1:8080/api/login)

请求方式：GET

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    token:'登录令牌',
}
```

请求参数：无

返回值：

```
    success:true,
    data:[
      {
        ID:1,
        DHID:1,
        SHID:1,
        Amount:'',
        YDDate:'2016-11-12',
        Remark:'',
      },
      ...
    ]
}
```

## 4.获取订购详情数据

访问路径URL:  [http://192.168.127.1:8080/api/ReserveDetial](http://192.168.127.1:8080/api/login)

请求方式：GET

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    token:'登录令牌',
}
```

请求参数：

| ID | 订购ID |
| :--- | :--- |


返回值：

```
    success:true,
    data:[
      {
        ID:1,
        YDID:1,
        SPID:1,
        Count:12,
        Price:123,
        Amount:'2017-12-8',
      },
      ...
    ]
}
```

## 5.获取账单数据

访问路径URL:  [http://192.168.127.1:8080/api/Bill](http://192.168.127.1:8080/api/login)

请求方式：GET

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    token:'登录令牌',
}
```

请求参数：无

返回值：

```
    success:true,
    data:[
      {
        billID:001,
        state:0/1/2,
      },
      ...
    ]
}
```

## 6.提交订购

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)submitOrder

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    token:'登录令牌',
}
```

请求参数：

| orderTarget | 订购目标 |
| :--- | :--- |
| orderNumber | 订购数量 |

返回值：

```
{    
    success:true,
}
```

## 7.修改密码

访问路径URL:  [http://192.168.127.1:8080/api/setPassword](http://192.168.127.1:8080/api/login)

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    token:'登录令牌',
}
```

请求参数：

| currentPwd | 旧密码 |
| :--- | :--- |
| targetPwd | 新密码 |

返回值：

```
{    
    success:true,
}
```

## 8.确认账单

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)confirmBill

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    token:'登录令牌',
}
```

请求参数：

| billID | 账单ID |
| :--- | :--- |
| state | 账单状态,为true或false |

返回值：

```
{    
    success:true,
}
```

## 9.退货

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)ReturnGoods

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    token:'登录令牌',
}
```

请求参数：

| ID | 订单详情ID |
| :--- | :--- |


返回值：

```
{    
    success:true,
}
```



