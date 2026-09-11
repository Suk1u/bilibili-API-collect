# 弹幕屏蔽词

## 查询屏蔽规则列表

> https://api.bilibili.com/x/dm/filter/user

*请求方式：GET*

鉴权方式：APP（access_key），需要 APP 签名，签名算法见 [APP API 签名](../misc/sign/APP.md)

需传入 APP 签名公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`），详见 [APP API 签名](../misc/sign/APP.md)

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| code    | num  | 返回值   | 0：成功 |
| message | str  | 错误信息 | 默认为0 |
| data    | obj  | 信息本体 |         |

`data`对象：

| 字段 | 类型  | 内容         | 备注 |
| ---- | ----- | ------------ | ---- |
| rule | array | 屏蔽规则列表 |      |

`data`中的`rule`数组：

| 项   | 类型 | 内容        | 备注 |
| ---- | ---- | ----------- | ---- |
| 0    | obj  | 屏蔽规则1   |      |
| n    | obj  | 屏蔽规则(n+1) |    |
| ……   | obj  | ……          | ……   |

`rule`数组中的对象：

| 字段    | 类型 | 内容           | 备注                       |
| ------- | ---- | -------------- | -------------------------- |
| id      | num  | 屏蔽规则 id    |                            |
| mid     | num  | 用户 mid       |                            |
| type    | num  | 屏蔽规则类型   | 见下表                     |
| filter  | str  | 屏蔽内容       | 规则类型为用户时为用户标识 |
| comment | str  | 备注           |                            |
| ctime   | num  | 创建时间       | 时间戳                     |
| mtime   | num  | 修改时间       | 时间戳                     |
| opened  | bool | 是否启用       |                            |

`type`属性值：

| 值 | 含义   | 备注                         |
| -- | ------ | ---------------------------- |
| 0  | 关键字 |                              |
| 1  | 正则   |                              |
| 2  | 用户   | 屏蔽该用户发送的弹幕         |

**示例：**

```shell
curl -G 'https://api.bilibili.com/x/dm/filter/user' \
--data-urlencode 'access_key=xxx' \
--data-urlencode 'appkey=xxx' \
--data-urlencode 'build=xxx' \
--data-urlencode 'mobi_app=android' \
--data-urlencode 'platform=android' \
--data-urlencode 'ts=0' \
--data-urlencode 'sign=xxx'
```

## 添加屏蔽规则

> https://api.bilibili.com/x/dm/filter/user/add

*请求方式：POST*

鉴权方式：APP（access_key），需要 APP 签名，签名算法见 [APP API 签名](../misc/sign/APP.md)

**正文参数（application/x-www-form-urlencoded）：**

| 参数名 | 类型 | 内容       | 必要性 | 备注                        |
| ------ | ---- | ---------- | ------ | --------------------------- |
| filter | str  | 屏蔽内容   | 必要   | 规则类型为用户时为用户标识  |
| type   | num  | 屏蔽规则类型 | 必要  | 0：关键字<br />1：正则<br />2：用户 |

除此之外还需传入 APP 签名公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`），详见 [APP API 签名](../misc/sign/APP.md)

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| code    | num  | 返回值   | 0：成功 |
| message | str  | 错误信息 | 默认为0 |
| data    | obj  | 信息本体 |         |

注：`data` 中字段作用尚不明确，响应结构待补充

**示例：**

添加关键字屏蔽规则`2333`

```shell
curl 'https://api.bilibili.com/x/dm/filter/user/add' \
--data-urlencode 'filter=2333' \
--data-urlencode 'type=0' \
--data-urlencode 'access_key=xxx' \
--data-urlencode 'appkey=xxx' \
--data-urlencode 'build=xxx' \
--data-urlencode 'mobi_app=android' \
--data-urlencode 'platform=android' \
--data-urlencode 'ts=0' \
--data-urlencode 'sign=xxx'
```
