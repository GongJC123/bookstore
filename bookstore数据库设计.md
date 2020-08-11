# 数据库设计

## 1. 分类表

多级目录，多级分类

### 字段：

| 名称              | 类型             | 描述                                               |
| :---------------- | ---------------- | :------------------------------------------------- |
| id                | integerField(11) | 分类id                                             |
| name              | charField(100)   | 分类名称                                           |
| root              | booleanField(1)  | 是否为根                                           |
| parentId          | integerField(11) | 外键指向自己                                       |
| children          | integerField(11) | 动态字段？？（多级列表）**递归嵌套，引入插件即可** |
| deleted(可选)     | (扩展)           | 逻辑删除                                           |
| create_time(可选) |                  |                                                    |
| update_time(可选) |                  |                                                    |



### 数据格式：

```json
[
    {
        "id": 2,
        "name": "程序设计",
        "root": true,
        "parentId": null,
        "children": [
            {
                "id": 6,
                "name": "C/C++",
                "root": false,
                "parentId": 2,
                "children": [
                    {
                        "id": 9,
                        "name": "C11",
                        "root": false,
                        "parentId": 6,
                        "children": []
                    }
                ]
            },
            {
                "id": 7,
                "name": "Java",
                "root": false,
                "parentId": 2,
                "children": []
            },
            {
                "id": 8,
                "name": "C#",
                "root": false,
                "parentId": 2,
                "children": []
            }
        ]
    }
]
```

## 2. 书籍商品表

注意图片处理即可

### 字段：

| 名称         | 类型             | 描述                     |
| ------------ | ---------------- | ------------------------ |
| id           | integerField(11) | id                       |
| title        | charField(100)   | 名称                     |
| author       | charField(100)   | 作者                     |
| price        | double?decimal   | 定价                     |
| discount     | decimal,float?   | 折扣                     |
| imgUrl       | image            | 图片                     |
| bigImgUrl    | image            | 大图                     |
| bookConcern  | charField(100)   | 出版社                   |
| publishDate  | dateField        | 出版日期                 |
| brief        | ???              | 简介？？？               |
| inventory    |                  | 库存                     |
| detail       |                  | 详情                     |
| newness      | booleanField     | 是否新品                 |
| hot          | booleanField     | 是否热销                 |
| specialOffer |                  | 限时特价，特别优惠       |
| slogan       |                  | 口号标语，广告           |
| category     | ？？？           | 类别（一对一？一对多？） |





### 数据格式

## 3. 评论表

| 名称        | 类型           | 描述             |
| ----------- | -------------- | ---------------- |
| id          | id             | id               |
| content     | textarea??     | 评论内容         |
| commentDate | date           | 评论时间         |
| username    | charField(100) | 当前评论，用户名 |
| book        | charField(100) | 书(id?name?)     |



## 4. 用户表

| 名称     | 类型             | 描述   |
| -------- | ---------------- | ------ |
| id       | integerField(11) | id     |
| username | charField(100)   | 用户名 |
| password | charField(100)   | 密码   |
| mobile   | integerField(11) | 手机号 |

# 二、项目创建

## 1. 安装pipenv

## 2. 用pipenv创建虚拟环境（换源）

## 3. 安装Django2.2.15版本

## 4. 修改settings.py中必要属性

## 5. 修改数据库连接

## 6. 按照教程添加依赖包[商城demo](https://www.cnblogs.com/derek1184405959/p/8747961.html)



