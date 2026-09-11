# 追番相关

## 追番
> https://api.bilibili.com/pgc/web/follow/add

*请求方式：POST*

鉴权方式：Cookie（SESSDATA）

**url参数：**

| 参数名      | 类型  | 内容     | 必要性 | 备注  |
|----------|-----|--------|-----|-----|
| season_id | str | 剧集ssid | 必要  |     |
| csrf | str | csrf token(位于cookies中的bili_jct) | 必要  |     |

**json回复：**

根对象：

| 字段    | 类型 | 内容   | 备注                            |
| ------- | ---- | ------ | ------------------------------- |
| code    | num  | 返回值 | 0：成功<br />-111：csrf校验失败 |
| message | str  | 信息   |            成功时：success                    |
| result | obj  |见下表|                                 |

根对象中的`result`对象：

| 字段     | 类型 | 内容       | 备注 |
| -------- | ---- | ---------- | ---- |
| fmid     | num  |      0      |      |
| relation | bool |        false    |      |
| status   | num  |        2    |      |
| toast    | str  | 自己追的番就要好好看完哟^o^ |      |

**示例：**

追番`ssid=41410`的番剧

```shell
curl -G 'https://api.bilibili.com/pgc/web/follow/add' \
--data-urlencode 'season_id=41410' \
--data-urlencode 'csrf=xxx' \
```

<details>

<summary>查看响应示例：</summary>

```json
{
  "code": 0,
  "message": "success",
  "result": {
    "fmid": 0,
    "relation": false,
    "status": 2,
    "toast": "自己追的番就要好好看完哟^o^"
  }
}
```
</details>

## 取消追番

> https://api.bilibili.com/pgc/web/follow/del

*请求方式：POST*

鉴权方式：Cookie（SESSDATA）

**url参数：**

| 参数名    | 类型 | 内容                                | 必要性 | 备注 |
| --------- | ---- | ----------------------------------- | ------ | ---- |
| season_id | str  | 剧集ssid                            | 必要   |      |
| csrf      | str  | csrf token(位于cookies中的bili_jct) | 必要   |      |

**json回复：**

根对象：

| 字段    | 类型 | 内容   | 备注                            |
| ------- | ---- | ------ | ------------------------------- |
| code    | num  | 返回值 | 0：成功<br />-111：csrf校验失败 |
| message | str  | 信息   |              成功时：success                  |
| result  | obj  | 见下表 |                                 |

根对象中的`result`对象：

| 字段     | 类型 | 内容       | 备注 |
| -------- | ---- | ---------- | ---- |
| fmid     | num  |       0     |      |
| relation | bool |     true       |      |
| status   | num  |     0       |      |
| toast    | str  | 已取消追番 |      |

**示例：**

取消`ssid=41410`的追番

```shell
curl -G 'https://api.bilibili.com/pgc/web/follow/del' \
--data-urlencode 'season_id=41410' \
--data-urlencode 'csrf=xxx' \
```

<details>

<summary>查看响应示例：</summary>

```json
{
  "code": 0,
  "message": "success",
  "result": {
    "fmid": 0,
    "relation": false,
    "status": 0,
    "toast": "已取消追番"
  }
}
```
</details>

## 追番_app端

> https://api.bilibili.com/pgc/app/follow/add

*请求方式：POST*

鉴权方式：APP（access_key）

需要 APP 签名（公共参数与签名算法见 [../misc/sign/APP.md](../misc/sign/APP.md)），下同

**正文参数（application/x-www-form-urlencoded）：**

仅列出业务参数，公共参数不列出

| 参数名    | 类型 | 内容    | 必要性 | 备注 |
| --------- | ---- | ------- | ------ | ---- |
| season_id | num  | 剧集ssid | 必要   |      |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| code    | num  | 返回值   | 0：成功 |
| message | str  | 错误信息 |         |
| result  | obj  | 信息本体 |         |

`result`对象：

| 字段 | 类型 | 内容         | 备注             |
| ---- | ---- | ------------ | ---------------- |
| toast | str | 操作提示文本 | 其余字段待补充   |

**示例：**

追番`ssid=41410`的番剧

```shell
curl 'https://api.bilibili.com/pgc/app/follow/add' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'season_id=41410' \
  --data-urlencode 'sign=xxx'
```

## 取消追番_app端

> https://api.bilibili.com/pgc/app/follow/del

*请求方式：POST*

鉴权方式：APP（access_key）

需要 APP 签名（公共参数与签名算法见 [../misc/sign/APP.md](../misc/sign/APP.md)）

**正文参数（application/x-www-form-urlencoded）：**

仅列出业务参数，公共参数不列出

| 参数名    | 类型 | 内容    | 必要性 | 备注 |
| --------- | ---- | ------- | ------ | ---- |
| season_id | num  | 剧集ssid | 必要   |      |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| code    | num  | 返回值   | 0：成功 |
| message | str  | 错误信息 |         |
| result  | obj  | 信息本体 |         |

`result`对象：

| 字段 | 类型 | 内容         | 备注             |
| ---- | ---- | ------------ | ---------------- |
| toast | str | 操作提示文本 | 其余字段待补充   |

**示例：**

取消`ssid=41410`的追番

```shell
curl 'https://api.bilibili.com/pgc/app/follow/del' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'season_id=41410' \
  --data-urlencode 'sign=xxx'
```

## 更新追番状态_app端

> https://api.bilibili.com/pgc/app/follow/status/update

*请求方式：POST*

鉴权方式：APP（access_key）

需要 APP 签名（公共参数与签名算法见 [../misc/sign/APP.md](../misc/sign/APP.md)）

**正文参数（application/x-www-form-urlencoded）：**

仅列出业务参数，公共参数不列出

| 参数名    | 类型 | 内容    | 必要性 | 备注                            |
| --------- | ---- | ------- | ------ | ------------------------------- |
| season_id | num  | 剧集ssid | 必要   |                                 |
| status    | num  | 追番状态 | 必要   | 1：想看<br />2：在看<br />3：看过 |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注           |
| ------- | ---- | -------- | -------------- |
| code    | num  | 返回值   | 0：成功        |
| message | str  | 错误信息 |                |
| result  | obj  | 信息本体 | 响应结构待补充 |

**示例：**

将`ssid=41410`的追番状态设为在看

```shell
curl 'https://api.bilibili.com/pgc/app/follow/status/update' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'season_id=41410' \
  --data-urlencode 'status=2' \
  --data-urlencode 'sign=xxx'
```

## 查询追番列表_app端

> https://api.bilibili.com/pgc/app/follow/v2/bangumi

*请求方式：GET*

鉴权方式：APP（access_key）

需要 APP 签名（公共参数与签名算法见 [../misc/sign/APP.md](../misc/sign/APP.md)）

**url参数：**

仅列出业务参数，公共参数不列出

| 参数名 | 类型 | 内容       | 必要性 | 备注                                              |
| ------ | ---- | ---------- | ------ | ------------------------------------------------- |
| pn     | num  | 页码       | 非必要 | 默认为 `1`                                        |
| ps     | num  | 每页项数   | 非必要 | 客户端默认为 `20`                                 |
| status | num  | 筛选状态   | 非必要 | 0：全部（默认）<br />1：想看<br />2：在看<br />3：看过 |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| code    | num  | 返回值   | 0：成功 |
| message | str  | 错误信息 |         |
| result  | obj  | 信息本体 |         |

`result`对象：

| 字段        | 类型  | 内容         | 备注                |
| ----------- | ----- | ------------ | ------------------- |
| follow_list | array | 追番列表     |                     |
| has_next    | num   | 是否有下一页 | 1：有<br />0：无    |

`result` 中的 `follow_list` 数组中的对象：

| 字段         | 类型 | 内容           | 备注 |
| ------------ | ---- | -------------- | ---- |
| badge        | str  | 角标文本       |      |
| cover        | str  | 封面图 URL     |      |
| new_ep       | obj  | 最新一话信息   |      |
| progress     | obj  | 观看进度       |      |
| season_id    | num  | 剧集ssid       |      |
| square_cover | str  | 方形封面图 URL |      |
| title        | str  | 剧集标题       |      |
| url          | str  | 剧集页面链接   |      |

`follow_list` 项中的 `new_ep` 对象：

| 字段       | 类型 | 内容           | 备注 |
| ---------- | ---- | -------------- | ---- |
| cover      | str  | 封面图 URL     |      |
| duration   | num  | 时长           |      |
| id         | num  | 分集ep id      |      |
| index_show | str  | 更新进度文本   |      |

`follow_list` 项中的 `progress` 对象：

| 字段       | 类型 | 内容               | 备注 |
| ---------- | ---- | ------------------ | ---- |
| index_show | str  | 观看进度文本       |      |
| last_ep_id | num  | 最后观看分集ep id  |      |

**示例：**

查询第 1 页全部追番

```shell
curl -G 'https://api.bilibili.com/pgc/app/follow/v2/bangumi' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'pn=1' \
  --data-urlencode 'ps=20' \
  --data-urlencode 'status=0' \
  --data-urlencode 'sign=xxx'
```

## 查询追影列表_app端

> https://api.bilibili.com/pgc/app/follow/v2/cinema

*请求方式：GET*

鉴权方式：APP（access_key）

需要 APP 签名（公共参数与签名算法见 [../misc/sign/APP.md](../misc/sign/APP.md)）

**url参数：**

仅列出业务参数，公共参数不列出

| 参数名 | 类型 | 内容       | 必要性 | 备注                                              |
| ------ | ---- | ---------- | ------ | ------------------------------------------------- |
| pn     | num  | 页码       | 非必要 | 默认为 `1`                                        |
| ps     | num  | 每页项数   | 非必要 | 客户端默认为 `20`                                 |
| status | num  | 筛选状态   | 非必要 | 0：全部（默认）<br />1：想看<br />2：在看<br />3：看过 |

**json回复：**

根对象：

| 字段    | 类型 | 内容     | 备注    |
| ------- | ---- | -------- | ------- |
| code    | num  | 返回值   | 0：成功 |
| message | str  | 错误信息 |         |
| result  | obj  | 信息本体 |         |

`result`对象：

| 字段        | 类型  | 内容         | 备注                |
| ----------- | ----- | ------------ | ------------------- |
| follow_list | array | 追影列表     |                     |
| has_next    | num   | 是否有下一页 | 1：有<br />0：无    |

`result` 中的 `follow_list` 数组中的对象：

| 字段         | 类型 | 内容           | 备注 |
| ------------ | ---- | -------------- | ---- |
| badge        | str  | 角标文本       |      |
| cover        | str  | 封面图 URL     |      |
| new_ep       | obj  | 最新一话信息   |      |
| progress     | obj  | 观看进度       |      |
| season_id    | num  | 剧集ssid       |      |
| square_cover | str  | 方形封面图 URL |      |
| title        | str  | 剧集标题       |      |
| url          | str  | 剧集页面链接   |      |

`follow_list` 项中的 `new_ep` 对象：

| 字段       | 类型 | 内容           | 备注 |
| ---------- | ---- | -------------- | ---- |
| cover      | str  | 封面图 URL     |      |
| duration   | num  | 时长           |      |
| id         | num  | 分集ep id      |      |
| index_show | str  | 更新进度文本   |      |

`follow_list` 项中的 `progress` 对象：

| 字段       | 类型 | 内容               | 备注 |
| ---------- | ---- | ------------------ | ---- |
| index_show | str  | 观看进度文本       |      |
| last_ep_id | num  | 最后观看分集ep id  |      |

**示例：**

查询第 1 页全部追影

```shell
curl -G 'https://api.bilibili.com/pgc/app/follow/v2/cinema' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'pn=1' \
  --data-urlencode 'ps=20' \
  --data-urlencode 'status=0' \
  --data-urlencode 'sign=xxx'
```
