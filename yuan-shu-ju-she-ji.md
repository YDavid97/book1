## 1.设计元数据

##### 元数据是App中基础业务数据，不可再分割。一个App根据业务需要，可能需要多个元数据支撑。

根据业务分析，此App需要4种元数据：

* UserInfo

* Room

* CheckItem

* CheckResult

#### UserInfo

```
{
    uid:'xxxx',
    token:'xxxxxx',
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :---: | :---: |
| uid | 用户唯一ID | 通过登陆请求获取 |
| token | 用户权限令牌 | 通过登陆请求获取 |

#### Room

```
{
    roomID:1,
    roomName:'101',
    roomType:0,
    roomTypeName:'宿舍',
    buildingID:1,
    buildingName:'1号楼',
    className:'16移动应用开发',
    teacherName:'小李',
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :---: | :---: |
| roomID | 房间主键ID | 房间唯一标识符，自增 |
| roomName | 房间名 |  |
| roomtype | 房间类型ID | 1宿舍，2为教室 |
| roomTypeName | 房间类型名称 |  |
| buildingID | 房间所属建筑物ID |  |
| buildingName | 房间所属建筑物名称 |  |
| className | 房间所属班级名称 |  |
| teacherName | 房间所属辅导员名称 |  |

#### CheckItem

```
{
    checkID:1,
    checkName:'地面卫生',
    roomType:0,
    sectionID:0,
    sectionName:'常规检查项',
    checkResult:true,
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :---: | :---: |
| checkID | 检查项ID | 唯一 |
| checkName | 检查项名称 |  |
| roomType | 检查项所属房间名称 |  |
| sectionID | 检查项类别ID | 0为常规检查项，1为安全检查项 |
| sectionName | 检查项类别名称 |  |
| checkResult | 检查结果 | true为合格，false为不合格 |

#### CheckResult

```
{
    room:room,
    checkItems:[
        checkItem,
        ...
    ],
    result:true,
    date:'时间字符串，格式为YYYY-MM-DD',
    submit:false,
}
```

#### 字段说明

| **字段名** | **作用** | **备注** |
| :---: | :--- | :--- |
| room | 房间元数据对象 |  |
| checkItems | 检查结果数据组，数组中每个元素为检查项元数据 |  |
| result | 房间检查结果 | 根据用户需求设定的检查规则对检查项进行计算，得出检查结果 |
| date | 检查时间 |  |
| submit | 检查结果是否上传服务器 | true未上传，false已上传 |



