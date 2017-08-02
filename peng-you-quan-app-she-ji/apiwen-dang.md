用户数据API接口文档

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

| name | 用户名 |
| :--- | :--- |
| pwd | 密码 |

返回值：

```
{
    success:true,
    data:{
            uid:'',
            token:'登录令牌',
        },
}
```

## 2.注册

访问路径URL:  [http://192.168.127.1:8080/api/register](http://192.168.127.1:8080/api/login)

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| name | 用户名 |
| :--- | :--- |
| pwd | 密码 |

返回值：

```
{
    success:true,
    token:'xxx',
}
```

## 3.修改密码

访问路径URL:  [http://192.168.127.1:8080/api/setPassword](http://192.168.127.1:8080/api/login)

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| currentPwd | 旧密码 |
| :--- | :--- |
| targetPwd | 新密码 |
| token | 用户令牌 |

返回值：

```
{    
    success:true,
}
```

## 4.获取指定消息

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)getNews

请求方式：GET

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| ids | id数组 |
| :--- | :--- |
| token | 用户令牌 |

返回值：

```
{    
    success:true,
    data:[
        {
            id:1,
            content:'xxx',
            createdAt:'2017-08-09';
            images:[
                {
                id:1,
                image:'xxx',
                },
                ...
            ],
            comment:[
                {
                    id:1,
                    content:'xxx',
                    Reviewer:
                        {
                            id:1,
                            name:'xxx',
                        },
                },
                ...
            ],
        }
    ]
}
```

## 5.获取好友列表

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)getFriends

请求方式：GET

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| token | 用户令牌 |
| :--- | :--- |


返回值：

```
{
    success:true,
    data:[
        {
            id:1,
            image:'xxx',
            autograph:'xxx',
        },
        ...
    ]
}
```

## 6.获取个人信息

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)getUserInfo

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| token | 用户令牌 |
| :--- | :--- |


返回值：

```
{    
    success:true,
    data:{
        id:'',
        nickname:'xxx',
        image:'xxx',
        autograph:'xxx',
    }
}
```

## 7.发送消息

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)sendMessage

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| content | 发送内容 |
| :--- | :--- |
| image1-9 | 图片 |
| token | 用户令牌 |

返回值：

```
{    
    success:true,
}
```

## 8.删除消息

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)deleteMessage

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| id | 删除消息id |
| :--- | :--- |
| token | 用户令牌用户令牌用户令牌用户 |

返回值：

```
{    
    success:true,
}
```

## 9.发送评论

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)sendComments

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| newsId | 要评论消息id |
| :--- | :--- |
| content | 评论内容 |
| token | 用户令牌 |

返回值：

```
{    
    success:true,
}
```

## 10.提交个人信息

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)postUserInfo

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| nickname | 昵称 |
| :--- | :--- |
| autograph | 个性签名 |
| image | 头像 |
| token | 用户令牌 |

返回值：

```
{    
    success:true,
}
```

## 11.关注好友

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)postUserInfo

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| id | 关注好友id |
| :--- | :--- |
| token | 用户令牌 |

返回值：

```
{    
    success:true,
}
```

## 12.忘记密码

访问路径URL:  [http://192.168.127.1:8080/api/forgetPassword](http://192.168.127.1:8080/api/login)

请求方式：POST

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| name | 用户名 |
| :--- | :--- |
| pwd | 新密码 |
| token | 用户令牌 |

返回值：

```
{    
    success:true,
    token:'xxx',
}
```

## 13.获取全部消息

访问路径URL:  [http://192.168.127.1:8080/api/](http://192.168.127.1:8080/api/login)getAllNews

请求方式：GET

请求头内容：

```
{
    'Accept': 'application/json',
    'Content-Type': 'application/json',
}
```

请求参数：

| token | 用户令牌 |
| :--- | :--- |


返回值：

```
{    
    success:true,
    data:[
        {
            id:1,
            content:'xxx',
            createdAt:'2017-08-09';
            images:[
                {
                id:1,
                image:'xxx',
                },
                ...
            ],
            comment:[
                {
                    id:1,
                    content:'xxx',
                    Reviewer:
                        {
                            id:1,
                            name:'xxx',
                        },
                },
                ...
            ],
        }
    ]
}
```



