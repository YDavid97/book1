# 设计数据服务对象

依照元数据设计，我们设计4个数据服务对象

* UserManager
* RoomManager
* CheckItemManager
* CheckResultManager

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

---

#### RoomManager

##### //更新本地Room数据

updateRoom\(resultCallBack\);

参数说明：

```
resultCallBack，为更新回调函数

(result,message)=>void

result：更新结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### 

##### //获取所有房间类型

getRoomType\(callBack\);

参数说明：

```
callBack为查询结果回调函数，类型为(roomTypes,message)=>void

roomTypes,查询结果数组，数组中每个元素为roomType对象
{
    roomTypeID:0,
    roomTypeName:'xxx',
}
当查询失败时，roomTypes值为null

message为失败原因
```

##### //通过房间类型，获取该类型下所有建筑物

getBuildings\(roomType,callBack\);

参数说明：

```
rooomType:房间类型ID

callBack为查询结果回调函数，类型为(buildings,message)=>void

buildings,查询结果数组，数组中每个元素为roomType对象
{
    buildingName:'xxx',
}
当查询失败时，buildings值为null

message为失败原因
```

##### //通过房间类型和建筑物名称获取所有房间

getRooms\(roomType,buildingName,callBack\);

参数说明：

```
roomType：房间类型ID

buildingName：建筑物名称

callBack为查询结果回调函数，类型为(rooms,message)=>void

rooms,查询结果数组，数组中每个元素为rooms对象

当查询失败时，rooms值为null

message为失败原因
```

---

#### CheckItemManager

##### //更新本地CheckItem数据

updateCheckItem\(resultCallBack\);

参数说明：

```
resultCallBack，为更新结果回调函数

(result,message)=>void

result：更新结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //通过房间对象，获取相应的检查项

getCheckItems\(room,callBack\);

参数说明：

```
callBack:为查询结果回调函数，类型为(checkItems,message)=>void

checkItems,查询结果数组，数组中每个元素为checkItems对象

当查询失败时，checkItems值为null

message为失败原因
```

---

#### CheckResultManager

##### //添加检查结果

addCheckResult\(checkResult,resultCallBack\);

参数说明：

```
checkResult：检查结果元数据

resultCallBack，为操作结果回调函数

(result,message)=>void

result：更新结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //保存修改后的检查结果

saveCheckResult\(checkResult,resultCallBack\);

参数说明：

```
checkResult：检查结果元数据

resultCallBack，为操作结果回调函数

(result,message)=>void

result：更新结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //删除检查结果

deleteCheckResult\(checkResultIDs,resultCallBack\);

参数说明：

```
checkResultIDs：检查结果ID数组

resultCallBack，为操作结果回调函数

(result,message)=>void

result：更新结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //根据roomType获取相应的检查结果

getCheckResult\(roomType,resultCallBack\);

参数说明：

```
roomType：房间类型ID

resultCallBack，为操作结果回调函数

(checkResults,message)=>void

checkResults：当前类型下的检查结果数组，数组中每一个元素为checkResult元数据对象

message:失败原因，当成功时，值为空
```

##### //提交检查结果到服务器

postCheckResults\(checkResultIDs,resultCallBack\);

参数说明：

```
checkResultIDs：检查结果ID数组

resultCallBack，为操作结果回调函数

(result,message)=>void

result：更新结果，true为成功,false为失败

message:失败原因，当成功时，值为空
```

##### //添加监听者，监听数据变化事件

addListener\(callBack\);

参数说明：

```
callBack，为操作结果回调函数，当数据发送变化时会调用

(void)=>void
```



