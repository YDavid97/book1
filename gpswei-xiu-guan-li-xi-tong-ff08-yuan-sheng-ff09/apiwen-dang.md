* [ ] ##### 返回值格式

```
{
    success：true/false
    date:{
            对象
        }
　　message:""如失败，需要给出原因,

}
```

## 1、登录

请求地址：47.93.20.76/api/Login

请求方式：POST

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| name | 用户名 |
| pwd | 密码 |

返回值：

```
{
   token://登录令牌
   uid://用户id
}
```

## 2、获取任务列表

请求地址：47.93.20.76/api/getWorkOrder

请求方式：POST

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| uid | 用户id |
| token | 用户令牌 |
| date | 今天的日期（可选择） |

返回值：

```
{
    success:true
    totle://总工单数
    done://完成数
    list:[
        {
           ID:
           userAddress://地址
           starttime://开始时间
           X://经度
           Y：//纬度

        }
    ]
    message:
}
```

## 3、提交任务状态

请求地址：47.93.20.76/api/OverState

请求方式：POST

请求参数：

| 参数名 | 参数说明 |
| :--- | :--- |
| uid | 用户id |
| token | 登录令牌 |
| id | 任务编号 |
| cntent | 维修情况 |
| state | 维修状态（0未完成  1完成） |

返回值：

```
{
    success:true/false
}
```



