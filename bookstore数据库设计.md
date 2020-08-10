# 数据库设计

## 1. 分类表

多级目录，多级分类

### 字段：

| 名称              | 类型         | 描述                                               |
| :---------------- | ------------ | :------------------------------------------------- |
| id                | int(11)      | 分类id                                             |
| name              | varchar(100) | 分类名称                                           |
| root              | bit(1)       | 是否为根                                           |
| parentId          | int(11)      | 外键指向自己                                       |
| children          | int(11)      | 动态字段？？（多级列表）**递归嵌套，引入插件即可** |
| deleted(可选)     | bit          | 逻辑删除                                           |
| create_time(可选) | date         |                                                    |
| update_time(可选) | date         |                                                    |



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

| 名称         | 类型 | 描述     |
| ------------ | ---- | -------- |
| id           |      | id       |
| title        |      | 名称     |
| author       |      | 作者     |
| price        |      | 定价     |
| discount     |      | 折扣     |
| imgUrl       |      | 图片     |
| bigImgUrl    |      | 大图     |
| bookConcern  |      | 出版社   |
| publishDate  |      | 出版日期 |
| brief        |      |          |
| inventory    |      |          |
| detail       |      |          |
| newness      |      |          |
| hot          |      |          |
| specialOffer |      |          |
| slogan       |      |          |
| category     |      |          |





### 数据格式

## 3. 评论表

| 名称        | 类型 | 描述             |
| ----------- | ---- | ---------------- |
| id          |      | id               |
| content     |      | 评论内容         |
| commentDate |      | 评论时间         |
| username    |      | 当前评论，用户名 |
| book        |      | 书               |



## 4. 用户表

| 名称     | 类型 | 描述 |
| -------- | ---- | ---- |
| id       |      |      |
| username |      |      |
| password |      |      |
| mobile   |      |      |

