# 设计数据服务对象

依照元数据设计，我们设计6个数据服务对象

* userManager
* FirendManafer
* NoticeManager

---

### userManager

##### //注册功能

register\(user,resltCallBack\);

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

##### 

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

##### 

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

### NoticeManager

##### //获取消息

##### getNotice\(,resultCallBack\);

##### //发送消息

##### //删除消息

##### //发送评论

---

### FirendManafer

##### //获取好友列表

##### //关注好友





