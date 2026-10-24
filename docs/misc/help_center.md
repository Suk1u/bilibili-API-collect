# 帮助中心

B 站网页版帮助中心（<https://www.bilibili.com/blackboard/help.html>）使用的接口，用于查询帮助中心的问题分类与问题内容。

## 查询帮助中心分类列表

> https://api.bilibili.com/x/web-goblin/help/list

*请求方式：GET*

**url参数：**

| 参数名        | 类型 | 内容             | 必要性 | 备注                               |
| ------------- | ---- | ---------------- | ------ | ---------------------------------- |
| parentTypeId | num  | 父分类id         | 必要   | 294：全部分类根                    |
| version      | num  | 版本             | 非必要 | 样本为1                            |

**json回复：**

根对象：

| 字段    | 类型  | 内容     | 备注    |
| ------- | ----- | -------- | ------- |
| code    | num   | 返回值   | 0：成功 |
| message | str   | 错误信息 | 默认为OK |
| ttl     | num   | 1        |         |
| data    | array | 分类列表 |         |

`data`数组中的对象：

| 字段              | 类型 | 内容         | 备注                                       |
| ----------------- | ---- | ------------ | ------------------------------------------ |
| questionTypeId    | str  | 分类id       |                                            |
| questionTypeName  | str  | 分类名称     | 如`首页`、`账号相关`                       |
| questionTypeDesc  | str  | 分类描述     | 如`二级分类`、`三级分类`                   |
| questionTypeStatus | num | 分类状态     | 1：启用                                    |
| parentTypeId      | str  | 父分类id     |                                            |
| typeLevel         | num  | 分类层级     | 2：二级<br />3：三级                       |
| sortNo            | num  | 排序序号     |                                            |
| last              | bool | 是否末级分类 | true：无子分类                             |

**示例：**

```shell
curl -G 'https://api.bilibili.com/x/web-goblin/help/list' \
--data-urlencode 'parentTypeId=294' \
--data-urlencode 'version=1'
```

<details>
<summary>查看响应示例：</summary>

```json
{
    "code": 0,
    "message": "OK",
    "ttl": 1,
    "data": [
        {
            "last": true,
            "parentTypeId": "294",
            "questionTypeDesc": "二级分类",
            "questionTypeId": "295",
            "questionTypeName": "首页",
            "questionTypeStatus": 1,
            "sortNo": 1,
            "typeLevel": 2
        },
        {
            "last": false,
            "parentTypeId": "294",
            "questionTypeDesc": "二级分类",
            "questionTypeId": "297",
            "questionTypeName": "播放器使用指南",
            "questionTypeStatus": 1,
            "sortNo": 4,
            "typeLevel": 2
        }
    ]
}
```

</details>

## 查询帮助中心问题列表

> https://api.bilibili.com/x/web-goblin/help/detail

*请求方式：GET*

**url参数：**

| 参数名         | 类型 | 内容     | 必要性 | 备注                               |
| -------------- | ---- | -------- | ------ | ---------------------------------- |
| questionTypeId | num  | 分类id   | 必要   |                                    |
| ps             | num  | 每页项数 | 必要   | 样本为20                           |
| version        | num  | 版本     | 非必要 | 样本为1                            |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| code    | num  | 返回值   | 0：成功 |
| message | str  | 错误信息 | 默认为OK |
| ttl     | num  | 1        |         |
| data    | obj  | 信息本体 |         |

`data`对象：

| 字段   | 类型  | 内容         | 备注                         |
| ------ | ----- | ------------ | ---------------------------- |
| detail | obj   | 问题列表详情 |                              |
| list   | array | 子分类列表   | 元素结构同`查询帮助中心分类列表` |

`data`中的`detail`对象：

| 字段  | 类型  | 内容     | 备注 |
| ----- | ----- | -------- | ---- |
| items | array | 问题列表 |      |
| page  | obj   | 分页信息 |      |

`detail`中的`items`数组中的对象：

| 字段             | 类型 | 内容           | 备注                                |
| ---------------- | ---- | -------------- | ----------------------------------- |
| questionId       | str  | 问题id         |                                     |
| questionTitle    | str  | 问题标题       |                                     |
| questionTypeId   | str  | 所属分类id     |                                     |
| questionTypeName | str  | 所属分类名称   |                                     |
| allTypeName      | str  | 完整分类路径   | 如`帮助中心/弹幕相关/弹幕礼仪`      |
| answerDesc       | str  | 答案内容       | 富文本html                          |
| answerTxt        | str  | 答案内容纯文本 |                                     |
| createId         | str  | 创建人         |                                     |
| createTime       | num  | 创建时间       | Unix时间戳(秒)                      |
| updateId         | str  | 更新人         |                                     |
| updateTime       | num  | 更新时间       | Unix时间戳(秒)                      |

`detail`中的`page`对象：

| 字段  | 类型 | 内容       | 备注 |
| ----- | ---- | ---------- | ---- |
| num   | num  | 当前页码   |      |
| size  | num  | 每页项数   |      |
| total | num  | 总项数     |      |

**示例：**

```shell
curl -G 'https://api.bilibili.com/x/web-goblin/help/detail' \
--data-urlencode 'questionTypeId=357' \
--data-urlencode 'ps=20' \
--data-urlencode 'version=1'
```

<details>
<summary>查看响应示例：</summary>

```json
{
    "code": 0,
    "message": "OK",
    "ttl": 1,
    "data": {
        "detail": {
            "items": [
                {
                    "allTypeName": "帮助中心/弹幕相关/弹幕礼仪",
                    "answerDesc": "<p>倡议内容</p>……",
                    "answerTxt": "倡议内容……",
                    "createId": "xinxin01",
                    "createTime": 1727245056,
                    "questionId": "4081",
                    "questionTitle": "弹幕礼仪相关",
                    "questionTypeId": "359",
                    "questionTypeName": "弹幕礼仪",
                    "updateId": "liuliu",
                    "updateTime": 1735193277
                }
            ],
            "page": {
                "num": 1,
                "size": 20,
                "total": 16
            }
        },
        "list": [
            {
                "last": true,
                "parentTypeId": "357",
                "questionTypeDesc": "三级分类",
                "questionTypeId": "358",
                "questionTypeName": "弹幕介绍",
                "questionTypeStatus": 1,
                "sortNo": 1,
                "typeLevel": 3
            }
        ]
    }
}
```

</details>
