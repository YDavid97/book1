# 设计元数据

根据业务分析，此App需要以下元数据：

* news         //消息对象
* personalInfo    //个人信息
* friends            //好友信息对象

#### news

```
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
```

#### personalInfo

```
{
    id:1,
    nickname:'xxx',
    image:'xxx',
    autograph:'xxx',
}
```

#### friends

```
{
    id:1,

}
```



