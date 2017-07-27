# 数据API接口文档 {#数据api接口文档}

### 1，登录 {#1，登录}

访问路径URL：`http://192.168.2.156:8089/api/Login`

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| name | 登录用户名 |
| :--- | :--- |
| pwd | 登录密码 |

返回值：

```
{
    success:true,
    id:"用户UID",
    token:"用户access_token"
}
```

### 2，获取Room数据 {#2，获取room数据}

访问路径URL：`http://192.168.2.156:8089/api/Room`

请求方式：GET

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    'timespan':"数据时间戳",
}
```

timespan为当前数据时间戳，用于更新数据信息。第一次请求是值为0。非第一次请是，填写上次数据返回的时间戳。

请求参数：无

返回值：

```
{
    success:true,
    timespan:'当前数据时间戳',//下次刷新数据是，需要提交这个时间戳
    datalist:[
        {
            roomID:1,
            roomName:'101',
            roomType:0,
            roomTypeName:'宿舍',
            buildingID:1,
            buildingName:'1号楼',
            className:'16移动应用开发',
            teacherName:'小李',
            state:'',//此字段非业务数据，只是标注当前数据处理状态'add','updata','delete'
        },
        ...
    ]
}
```

### 3，获取检查项 {#3，获取检查项}

请求路径URL：`http://192.168.2.156:8089/api/CkeckItem`

请求方式：GET

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    'timespan':"时间戳",
}
```

请求参数：无

返回值：

```
{
    success:true,
    timespan:'当前数据时间戳',//下次刷新数据是，需要提交这个时间戳
    datalist:[
        {
            checkID:1,
            checkName:'地面卫生',
            roomType:0,
            sectionID:0,
            sectionName:'常规检查项',
            state:'',//此字段非业务数据，只是标注当前数据处理状态'add','updata','delete'
        },
        ...
    ]
}
```

### 4，提交检查结果 {#4，提交检查结果}

请求URL：`http://192.168.2.156:8089/api/CheckRecord`

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    'uid':'你的uid',
    'token':'你的token',
}
```

提交参数，检查结果数组，

```
[
    checkResult1,
]
```

提交元数据说明

```
{
    room:{
        roomID:1,
    },
    checkItems:[
        {
            checkID:1,
            checkState:true,
            checkImage:'base64格式的图片',//可选字段
        },
        ...
    ],
    result:true,
    date:'时间字符串，格式为YYYY-MM-DD'
}
```

返回值：

```
{
    success:true,
}
```



