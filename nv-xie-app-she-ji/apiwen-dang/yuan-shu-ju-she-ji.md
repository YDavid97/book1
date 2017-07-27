# 设计元数据

根据业务分析，此App需要以下元数据：

* Product        //商品对象
* PreOrder      //预定信息对象
* Order            //订单对象
* OrderDetail  //订单明细对象
* BillDetail      //账单明细对象
* Bill                //对账单对象
* Notice          //通知对象

---

### Product

```
{

    id:101,
    name:'',
    summary:'',
    image:'imageURL',
    code:,
    price:,
    colors:[
            {
                id:'颜色id',
                name:'颜色名称'
            },
            ...
        ],
    sizes:[
            {
                id:'尺码id',
                name:'尺码名称'
            },
            ...

        ],
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :--- | :--- | :--- |
| id | 商品id |  |
| name | 商品名称 |  |
| summary | 商品简介 |  |
| image | 商品图片链接 |  |
| code | 商品编码，例如3014， |  |
| price | 商品价格 |  |
| colors | 商品颜色数组 | 数组中包括多个颜色对象， |
| sizes | 商品尺码数组 | 数组中包括多个尺码对象 |

---

### PreOrder

```
{ 
    id:101,
    date:'',
    productID:,
    name:'',
    code:'',
    image:'',
    price:,
    count:,
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :--- | :--- | :--- |
| id | 预定信息id |  |
| date | 预定时间 |  |
| productID | 商品ID |  |
| name | 商品名称 |  |
| code | 产品编码 |  |
| image | 商品图片链接 |  |
| price | 价格 |  |
| count | 预定数量 |  |

---

### Order

```
{
    id:,
    date:,
    totalPrice:,
    type:'订单类型'
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :--- | :--- | :--- |
| id | 订单id |  |
| date | 订单日期 |  |
| totalPrice | 总价 |  |
| type | 订单状态 | 0未确认订单，1已确认订单，2已发货订单 |

---

### OrderDetail

```
{
    id:订单明细id,
    productID:商品类型ID,
    productName:商品名称,
    productCode:商品编码,
    productColorID:,
    productColorName:,
    productSizeID:,
    productSizeName:,
    count:,,
    price:,
    totalPrice:,
    type:'订单明细类型'
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :--- | :--- | :--- |
| id | 订单明细id |  |
| productID | 商品id |  |
| productName | 商品名称 |  |
| productCode | 商品编号 |  |
| productColorID | 商品颜色id |  |
| productColorName | 商品颜色名称 |  |
| productSizeID | 商品尺码 |  |
| productSizeName | 商品尺码大小 |  |
| count | 数量 |  |
| price | 价格 |  |
| totalPrice | 总价 |  |
| type | 订单明细类型 | 0正常，1退货申请中，2退货成功，3退货失败，4换货申请中，5换货成功，6换货失败 |

---

### BillDetail

```
{
    id:
    date:
    totalPrice:
    orderID:
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :--- | :--- | :--- |
| id | 账单明细id |  |
| date | 生成帐单时间 |  |
| totalPrice | 总价 |  |
| orderID | 订单ID |  |

---

### Bill

```
{
    id:,
    date:,
    orderTotalPrice:,
    backTotalPrice:,
    money:,
    type:'',
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :--- | :--- | :--- |
| id | 对账单id |  |
| date | 账单日期 |  |
| orderTotalPrice | 订单总金额 |  |
| backTotalPrice | 退货总金额 |  |
| money | 应付账款 |  |
| type | 账单类型 | 0未确认，1已确认，2已付款 |

---

### Notice

```
{
    id:,
    title:,
    content:,
    date:,
    type:'',
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :--- | :--- | :--- |
| id | 通知id |  |
| title | 通知标题 |  |
| content | 通知内容 |  |
| date | 通知日期 |  |
| type | 通知类型 | 0为公共，1为个人 |



