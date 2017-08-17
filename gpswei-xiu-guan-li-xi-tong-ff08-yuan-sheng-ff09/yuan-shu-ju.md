# 元数据

返回格式

```
{
    success:true/false,
    data:[
        对象
    ],
    message:'错误提示信息',
}
```

登陆信息

```
{
    id:
    name:
    img:
    company:
}
```

订单信息

```
{
    orderCount, //订单数
    orderfinishedCount,  //订单完成的数量
    list,  //订单的集合
}
```

订单详情

```
{
    orderId,  //订单号
    orderAddress,  //订单地址
    orderDate,  //订单日期
    X  //终点的经度
    Y  //终点的纬度
}
```

维修情况

```
{
    orderId:
    content:
    state: 
}
```



