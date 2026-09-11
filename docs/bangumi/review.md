# 剧集短评

## 查询短评列表

> https://api.bilibili.com/pgc/review/short/list

*请求方式：GET*

无需登录，登录后可附带 access_key 获取与当前用户相关的数据（如点赞、点踩状态）

**url参数：**

| 参数名    | 类型 | 内容       | 必要性 | 备注                                       |
| --------- | ---- | ---------- | ------ | ------------------------------------------ |
| media_id  | num  | 剧集 md id | 必要   |                                            |
| ps        | num  | 每页项数   | 非必要 | 客户端固定为 `20`                          |
| sort      | num  | 排序方式   | 非必要 | 客户端默认传 `0`，具体枚举值待确认         |
| cursor    | str  | 翻页游标   | 非必要 | 首页不传，翻页时传上页响应中的 `next` 字段 |
| access_key | str | APP 登录令牌 | 非必要 | 登录后附带                                 |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注           |
| ------- | ---- | -------- | -------------- |
| code    | num  | 返回值   | 0：成功        |
| message | str  | 错误信息 |                |
| data    | obj  | 信息本体 |                |

`data` 对象：

| 字段 | 类型  | 内容       | 备注                 |
| ---- | ----- | ---------- | -------------------- |
| list | array | 短评列表   |                      |
| next | str   | 下一页游标 | 用于翻页             |
| total | num  | 短评总数   |                      |

`data` 中的 `list` 数组中的对象：

| 字段      | 类型 | 内容           | 备注                   |
| --------- | ---- | -------------- | ---------------------- |
| author    | obj  | 评论用户信息   |                        |
| content   | str  | 评论内容       |                        |
| ctime     | num  | 评论发布时间戳 |                        |
| mid       | num  | 评论用户 mid   | 与 `author.mid` 相同   |
| progress  | str  | 观看进度       |                        |
| review_id | num  | 短评 ID        |                        |
| score     | num  | 评分           | 10 分制                |
| stat      | obj  | 评论互动信息   |                        |

`list` 项中的 `author` 对象：

| 字段  | 类型 | 内容         | 备注 |
| ----- | ---- | ------------ | ---- |
| avatar | str | 用户头像 URL |      |
| mid    | num  | 用户 mid     |      |
| uname  | str  | 用户昵称     |      |
| vip    | obj  | 会员信息     |      |

`author` 中的 `vip` 对象：

| 字段       | 类型 | 内容     | 备注                     |
| ---------- | ---- | -------- | ------------------------ |
| vip_status | num  | 会员状态 |                          |
| vip_type   | num  | 会员类型 | 具体枚举值待确认         |

`list` 项中的 `stat` 对象：

| 字段     | 类型 | 内容             | 备注                |
| -------- | ---- | ---------------- | ------------------- |
| disliked | num  | 是否已点踩       | 0：否<br />1：是    |
| liked    | num  | 是否已点赞       | 0：否<br />1：是    |
| likes    | num  | 点赞数           |                     |

**示例：**

查询 `media_id=28233839` 的短评列表

```shell
curl -G 'https://api.bilibili.com/pgc/review/short/list' \
  --data-urlencode 'media_id=28233839' \
  --data-urlencode 'ps=20' \
  --data-urlencode 'sort=0'
```

## 点赞短评

> https://api.bilibili.com/pgc/review/action/like

*请求方式：POST*

鉴权方式：APP（access_key）

需要 APP 签名（公共参数与签名算法见 [../misc/sign/APP.md](../misc/sign/APP.md)），下同

**正文参数（application/x-www-form-urlencoded）：**

仅列出业务参数，公共参数不列出

| 参数名      | 类型 | 内容       | 必要性 | 备注                 |
| ----------- | ---- | ---------- | ------ | -------------------- |
| media_id    | num  | 剧集 md id | 必要   |                      |
| review_id   | num  | 评论 ID    | 必要   |                      |
| review_type | num  | 评论类型   | 必要   | 1：长评<br />2：短评 |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| code    | num  | 返回值   | 0：成功 |
| message | str  | 错误信息 |         |
| data    | obj  | 信息本体 |         |

`data` 对象：

| 字段   | 类型 | 内容     | 备注                    |
| ------ | ---- | -------- | ----------------------- |
| status | num  | 点赞状态 | 1：已点赞<br />0：未点赞 |

**示例：**

点赞 `media_id=28233839` 下的短评 `review_id=12345678`

```shell
curl 'https://api.bilibili.com/pgc/review/action/like' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'media_id=28233839' \
  --data-urlencode 'review_id=12345678' \
  --data-urlencode 'review_type=2' \
  --data-urlencode 'sign=xxx'
```

## 点踩短评

> https://api.bilibili.com/pgc/review/action/dislike

*请求方式：POST*

鉴权方式：APP（access_key）

需要 APP 签名（公共参数与签名算法见 [../misc/sign/APP.md](../misc/sign/APP.md)）

**正文参数（application/x-www-form-urlencoded）：**

仅列出业务参数，公共参数不列出

| 参数名      | 类型 | 内容       | 必要性 | 备注                 |
| ----------- | ---- | ---------- | ------ | -------------------- |
| media_id    | num  | 剧集 md id | 必要   |                      |
| review_id   | num  | 评论 ID    | 必要   |                      |
| review_type | num  | 评论类型   | 必要   | 1：长评<br />2：短评 |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| code    | num  | 返回值   | 0：成功 |
| message | str  | 错误信息 |         |
| data    | obj  | 信息本体 |         |

`data` 对象：

| 字段   | 类型 | 内容     | 备注                    |
| ------ | ---- | -------- | ----------------------- |
| status | num  | 点踩状态 | 1：已点踩<br />0：未点踩 |

**示例：**

点踩 `media_id=28233839` 下的短评 `review_id=12345678`

```shell
curl 'https://api.bilibili.com/pgc/review/action/dislike' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'media_id=28233839' \
  --data-urlencode 'review_id=12345678' \
  --data-urlencode 'review_type=2' \
  --data-urlencode 'sign=xxx'
```

## 发表短评

> https://api.bilibili.com/pgc/review/action/short/post

*请求方式：POST*

鉴权方式：APP（access_key）

需要 APP 签名（公共参数与签名算法见 [../misc/sign/APP.md](../misc/sign/APP.md)）

**正文参数（application/x-www-form-urlencoded）：**

仅列出业务参数，公共参数不列出

| 参数名     | 类型 | 内容             | 必要性 | 备注                  |
| ---------- | ---- | ---------------- | ------ | --------------------- |
| media_id   | num  | 剧集 md id       | 必要   |                       |
| content    | str  | 评论内容         | 必要   | 需 URL 编码           |
| share_feed | num  | 是否同步发动态   | 非必要 | 0：否<br />1：是      |
| score      | num  | 评分             | 必要   | 10 分制               |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注                  |
| ------- | ---- | -------- | --------------------- |
| code    | num  | 返回值   | 0：成功               |
| message | str  | 错误信息 |                       |
| result  | obj  | 信息本体 | 响应结构待补充        |

**示例：**

对 `media_id=28233839` 发表 10 分短评

```shell
curl 'https://api.bilibili.com/pgc/review/action/short/post' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'media_id=28233839' \
  --data-urlencode 'content=非常好看了' \
  --data-urlencode 'share_feed=0' \
  --data-urlencode 'score=10' \
  --data-urlencode 'sign=xxx'
```
