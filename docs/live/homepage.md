# 直播首页相关接口

## 获取首页中心入口显示状态

> https://api.live.bilibili.com/xlive/mcn-interface/v1/homePage/CenterEntryIsShow

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| 无 | | | | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| ttl | num | 1 | |
| data | obj | 信息本体 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| activity_card_v2 | obj | 活动卡片V2 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| navbar | bool | 是否显示导航栏 | |
| sidebar | bool | 是否显示侧边栏 | |
| footer | bool | 是否显示页脚 | |
| url | str | 中心入口URL | |

**示例:**

```shell
curl 'https://api.live.bilibili.com/xlive/mcn-interface/v1/homePage/CenterEntryIsShow'
```

<details>
<summary>查看响应示例:</summary>

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "navbar": true,
    "sidebar": true,
    "footer": true,
    "url": "https://live.bilibili.com/galaxy"
  }
}
```

</details>

---

## 获取新版排行榜顶部

> https://api.live.bilibili.com/room/v2/Index/getNewRankTop

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| type | str | 排行榜类型 | 非必要 | 如: guard |
| web_location | str | Web位置 | 非必要 | 如: 444.7 |
| w_rid | str | WBI签名 | 非必要 | |
| wts | num | 时间戳 | 非必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | array | 排行榜数据 | |

`data`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| room_id | num | 直播间ID | |
| uid | num | 主播UID | |
| online | num | 在线人数 | |
| title | str | 直播间标题 | |
| flag | num | 标志 | |
| watched_show | obj | 观看数据显示 | |
| face | str | 主播头像 | |
| uname | str | 主播昵称 | |
| is_verify | num | 是否认证 | |
| is_nft | num | 是否NFT | |
| nft_dmark | str | NFT标识 | |
| room_head_box | str | 房间头像框 | |
| box_type | num | 框类型 | |

**示例:**

```shell
curl -G 'https://api.live.bilibili.com/room/v2/Index/getNewRankTop' \
--data-urlencode 'type=guard'
```

---

## 获取导航信息

> https://api.live.bilibili.com/room/v2/Index/getNavigate

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| web_location | str | Web位置 | 非必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | array | 导航数据 | |

---

## 获取热门排行榜

> https://api.live.bilibili.com/xlive/web-interface/v1/index/getHotRankList

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| w_rid | str | WBI签名 | 非必要 | |
| wts | num | 时间戳 | 非必要 | |
| web_location | str | Web位置 | 非必要 | 如: 444.7 |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 信息本体 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| list | array | 排行榜列表 | |
| count | num | 总数 | |

`list`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| roomid | num | 直播间ID | |
| uid | num | 主播UID | |
| uname | str | 主播昵称 | |
| face | str | 主播头像 | |
| title | str | 直播间标题 | |
| area_v2_id | num | 分区ID | |
| area_v2_name | str | 分区名称 | |
| area_v2_parent_name | str | 父分区名称 | |
| area_v2_parent_id | num | 父分区ID | |
| online | num | 在线人数 | |
| live_status | num | 直播状态 | 1: 直播中 |
| rank | num | 排名 | |
| user_num | num | 助力人数 | |
| user_num_text | str | 助力人数文本 | |
| score | num | 分数 | |
| score_text | str | 分数文本 | |
| head_box | obj | 头像框信息 | |
| head_box_type | num | 头像框类型 | |

---

## 获取Web分区列表

> https://api.live.bilibili.com/xlive/web-interface/v1/index/getWebAreaList

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| web_location | str | Web位置 | 非必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | array | 分区列表 | |
| expid | num | 实验ID | 未知 |

---

## 获取直播列表

> https://api.live.bilibili.com/xlive/web-interface/v1/index/getList

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| web_location | str | Web位置 | 非必要 | |
| w_rid | str | WBI签名 | 非必要 | |
| wts | num | 时间戳 | 非必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 信息本体 | |

---

## 获取分区遮罩

> https://api.live.bilibili.com/xlive/web-interface/v1/index/getAreaMask

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| web_location | str | Web位置 | 非必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 遮罩信息 | |

---

## 获取直播首页全部列表_app端

> https://api.live.bilibili.com/xlive/app-interface/v2/index/getAllList

*请求方式: GET*

鉴权方式: APP（access_key）

获取直播首页信息（banner、分区入口等），需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

注: 仅有 `mobi_app=android` 时才能获取到 `area_entrance_v2` 字段

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| device | str | 设备类型 | 必要 | 固定为 `android` |
| rec_page | num | 推荐页码 | 必要 | 默认为 `1` |
| relation_page | num | 关注页码 | 必要 | 默认为 `1` |
| scale | str | 分辨率标识 | 必要 | 如 `xxhdpi` |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 信息本体 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| banner | array | 首页banner列表 | 每项含 `list` 字段为banner列表 |
| area_entrance_v2 | array | 分区入口列表 | 每项含 `list` 字段为分区入口列表<br />仅 `mobi_app=android` 时返回 |

`data.banner`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| list | array | banner列表 | |

`data.banner[].list`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | banner id | |
| title | str | banner标题 | |
| pic | str | banner图片url | |
| link | str | 跳转链接 | |

`data.area_entrance_v2`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| list | array | 分区入口列表 | |

`data.area_entrance_v2[].list`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 入口 id | |
| area_v2_id | num | 直播子分区id | |
| area_v2_parent_id | num | 直播父分区id | |
| tag_type | num | 标签类型 | |
| title | str | 入口标题 | |
| pic | str | 入口图片url | |
| link | str | 跳转链接 | |

注: 响应中可能还存在推荐直播间等其他字段，响应结构待补充

**示例:**

```shell
curl -G 'https://api.live.bilibili.com/xlive/app-interface/v2/index/getAllList' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'device=android' \
  --data-urlencode 'rec_page=1' \
  --data-urlencode 'relation_page=1' \
  --data-urlencode 'scale=xxhdpi' \
  --data-urlencode 'sign=xxx'
```
