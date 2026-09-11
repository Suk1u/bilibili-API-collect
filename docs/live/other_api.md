# 直播其他接口

## 获取直播间屏蔽信息

> https://api.live.bilibili.com/banned_service/v1/shield/get_shield_info

*请求方式：GET*

认证方式：Cookie

**URL参数：**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| room_id | num | 直播间ID | 必要 | |

**json回复：**

根对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0：成功 |
| message | str | 错误信息 | |
| data | obj | 屏蔽信息 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| shield_user_list | array | 屏蔽用户列表 | |
| keyword_list | array | 屏蔽关键词列表 | |
| shield_rules | obj | 屏蔽规则 | |

`data.shield_rules`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| rank | num | 等级限制 | 低于该等级的用户被屏蔽 |
| verify | num | 认证限制 | 0：不限制<br/>1：限制未认证用户 |
| level | num | 等级限制 | 未知 |

---

## 获取客户端资源

> https://api.live.bilibili.com/xlive/open-interface/v1/fetch_client_resource

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| web_location | str | Web位置 | 非必要 | |
| room_id | num | 直播间ID | 非必要 | |
| ruid | num | 主播UID | 非必要 | |
| page_source | num | 页面来源 | 非必要 | |
| platform | str | 平台 | 非必要 | pc |
| position | num | 位置 | 非必要 | |
| position_flag | num | 位置标识 | 非必要 | |
| source | str | 来源 | 非必要 | |
| csrf | str | CSRF Token | 非必要 | |
| w_rid | str | WBI签名 | 非必要 | |
| wts | num | 时间戳 | 非必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 资源信息 | |

---

## 获取收益MD5

> https://api.live.bilibili.com/xlive/general-interface/v1/content/getRevenueMd5

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
| data | obj | MD5信息 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| wealth | str | 财富值MD5 | |

---

## 获取内容

> https://api.live.bilibili.com/xlive/general-interface/v1/content/get

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
| data | obj | 内容数据 | |

---

## 获取追踪配置

> https://api.live.bilibili.com/xlive/open-interface/v2/tracker/conf

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
| data | obj | 追踪配置 | |

---

## 获取RTC时间戳

> https://api.live.bilibili.com/xlive/open-interface/v1/rtc/getTimestamp

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
| data | obj | 时间戳信息 | |

---

## 查询资源

> https://api.live.bilibili.com/xlive/open-interface/v1/query_resource

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| module | str | 资源模块名 | 必要 | 多个模块用逗号分隔，可选值: `medal_icon`/`medal`/`guard_resource`/`medal_level_up_animation` |
| web_location | str | Web位置 | 非必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 资源数据 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| hash | str | 资源哈希 | |
| kv | obj | KV配置数据 | |
| medal_icon | obj | 勋章图标资源 | |
| birthday | obj | 生日相关数据 | |
| guard_resource | obj | 舰长资源 | |
| guard_resource_new | obj | 新版舰长资源 | |
| medal | obj | 勋章数据 | |
| medal_level_up_animation | obj | 勋章升级动画数据 | |

`data.kv`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| hash | str | 哈希 | |
| data | obj | KV数据 | |

`data.kv.data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| web | str | Web端配置 | |

`data.medal_icon`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| hash | str | 哈希 | |
| hover | str | 悬浮图标 | |
| data | array | 图标数据列表 | |
| honor | str | 荣誉图标 | 为空时为null |
| guard_honor | str | 舰长荣誉图标 | 为空时为null |
| guard_icon | obj | 舰长图标 | 为空时为null |
| light_honor | str | 点亮荣誉图标 | |
| thousand_guard_icon | obj | 千舰图标 | 为空时为null |
| thousand_guard_uid | array | 千舰用户UID列表 | 为空时为null |

`data.medal_icon.guard_icon`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| 1 | str | 督察舰长图标 | |
| 2 | str | 舰长图标 | |
| 3 | str | 提督图标 | |

`data.medal_icon.thousand_guard_icon`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| 1 | str | 千舰图标1 | |
| 2 | str | 千舰图标2 | |
| 3 | str | 千舰图标3 | |

`data.birthday`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| hash | str | 哈希 | |
| data | array | 生日数据列表 | |

`data.guard_resource`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| hash | str | 哈希 | |
| data | obj | 舰长资源数据 | 未请求该模块时为null |

`data.guard_resource.data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| guard_1_1 | str | 督察舰长图标1 | |
| guard_1_2 | str | 督察舰长图标2 | |
| guard_1_3 | str | 督察舰长图标3 | |
| guard_2_1 | str | 舰长图标1 | |
| guard_2_2 | str | 舰长图标2 | |
| guard_2_3 | str | 舰长图标3 | |
| guard_3_1 | str | 提督图标1 | |
| guard_3_2 | str | 提督图标2 | |
| guard_3_3 | str | 提督图标3 | |
| list_bg_2 | str | 舰长列表背景 | |
| list_bg_3 | str | 提督列表背景 | |
| rhombus_2 | str | 舰长菱形图标 | |
| rhombus_3 | str | 提督菱形图标 | |
| buy_guard_2 | str | 购买舰长页面背景 | |
| buy_guard_3 | str | 购买提督页面背景 | |
| dialog_bg_2 | str | 舰长对话框背景 | |
| dialog_bg_3 | str | 提督对话框背景 | |
| anchor_dialog_bg_2 | str | 主播舰长对话框背景 | |
| anchor_dialog_bg_3 | str | 主播提督对话框背景 | |
| color_highlight_2 | str | 舰长高亮色 | |
| color_minor_2 | str | 舰长次要色 | |
| color_name_2 | str | 舰长名称色 | |
| color_highlight_3 | str | 提督高亮色 | |
| color_minor_3 | str | 提督次要色 | |
| color_name_3 | str | 提督名称色 | |
| log_icon_2 | str | 舰长日志图标 | |
| log_icon_3 | str | 提督日志图标 | |
| guard_log_icon_2 | str | 舰长日志舰长图标 | |
| guard_log_icon_3 | str | 提督日志舰长图标 | |
| log_color_highlight_2 | str | 舰长日志高亮色 | |
| log_color_highlight_3 | str | 提督日志高亮色 | |

`data.guard_resource_new`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| hash | str | 哈希 | |
| data | array | 新版舰长资源数据列表 | |

`data.medal`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| hash | str | 哈希 | |
| data | obj | 勋章详细数据 | 未请求该模块时为null |

`data.medal.data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| normal | array | 普通勋章列表 | |
| guard | array | 舰长勋章列表 | |
| honor | array | 荣誉勋章列表 | |
| honor_level_icon | array | 荣誉等级图标列表 | |
| honor_guard_level_icon | array | 荣誉舰长等级图标列表 | |

`data.medal_level_up_animation`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| hash | str | 哈希 | |
| data | obj | 升级动画数据 | 未请求该模块时为null |

`data.medal_level_up_animation.data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| animation | array | 动画数据列表 | |

---

## 获取抽奖信息

> https://api.live.bilibili.com/xlive/lottery-interface/v1/lottery/getLotteryInfoWeb

*请求方式: GET*

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| roomid | num | 直播间ID | 必要 | |
| web_location | str | Web位置 | 非必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 抽奖信息 | |

---

## 获取全屏特效配置

> https://api.live.bilibili.com/xlive/general-interface/v1/fullScSpecialEffect/GetEffectConfListV2

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
| data | obj | 特效配置 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| full_sc_resource | obj | 全屏特效资源 | |
| float_sc_resource | obj | 浮动特效资源 | |

`data.full_sc_resource`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| conf_list | array | 配置列表 | |
| base_version | num | 基础版本号 | |
| ttl | num | 缓存时间 | |

---

## 数据接口

> https://api.live.bilibili.com/xlive/data-interface/v1/x25Kn/E

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
| data | obj | 数据 | |

---

## 获取购物车状态

> https://api.live.bilibili.com/xlive/e-commerce-interface/v1/ecommerce-user/get_shopping_cart_status

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
| data | obj | 购物车状态 | |

---

## 获取Widget横幅列表

> https://api.live.bilibili.com/xlive/play-interface/widgetService/GetWidgetBannerList

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
| data | obj | 横幅列表 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| banner_list | array | 横幅列表 | |
| widget_list | array | 小组件列表 | |
| banner_list_entrance | array | 横幅入口列表 | |
| popup_config | null | 弹窗配置 | |

`data.banner_list`数组中的对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 横幅ID | |
| name | str | 名称 | |
| main_pic | str | 主图URL | |
| icon | str | 图标URL | |
| icon_v2 | str | 图标V2 URL | |
| jump_url | str | 跳转URL | |
| jump_type | num | 跳转类型 | |
| online_time | str | 上线时间 | |
| offline_time | str | 下线时间 | |
| weight | num | 权重 | |
| show_type | num | 展示类型 | |
| show_strategy | num | 展示策略 | |
| activity_type | num | 活动类型 | |
| icon_type | num | 图标类型 | |
| extra | str | 额外信息 | |
| business_type | num | 业务类型 | |
| badge | null | 徽章 | |
| entrance_icon | str | 入口图标URL | |
| entrance_jump_url | str | 入口跳转URL | |
| entrance_type | num | 入口类型 | |

`data.widget_list`数组中的对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| widget_type | num | 小组件类型 | |
| widget_config | obj | 小组件配置 | |

`data.widget_list[].widget_config`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| jump_url | str | 跳转URL | |
| icon | str | 图标URL | |
| title | str | 标题 | |
| subtitle | str | 副标题 | |
| online_time | str | 上线时间 | |
| offline_time | str | 下线时间 | |
| weight | num | 权重 | |

`data.banner_list_entrance`数组中的对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| icon | str | 图标URL | |
| jump_url | str | 跳转URL | |
| name | str | 名称 | |
| online_time | str | 上线时间 | |
| offline_time | str | 下线时间 | |
| weight | num | 权重 | |
| show_type | num | 展示类型 | |
| show_strategy | num | 展示策略 | |
| badge | null | 徽章 | |

---

## 获取背景列表

> https://api.live.bilibili.com/room/v1/Bg/get_list

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
| data | array | 背景列表 | |

---

## 主播检查

> https://api.live.bilibili.com/xlive/lottery-interface/v1/Anchor/Check

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
| data | obj | 检查结果 | |

---

## 获取大乱斗时间戳

> https://api.live.bilibili.com/xlive/general-interface/v1/battle/getTimestamp

*请求方式: GET*

认证方式：无（无需Cookie）

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| platform | str | 平台 | 必要 | pc |
| timestamp | num | 时间戳 | 必要 | 13位毫秒时间戳 |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| ttl | num | 未知 | |
| data | obj | 数据 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| timestamp | num | 服务器时间戳 | 13位毫秒时间戳，用于大乱斗功能的时间校验 |

---

## 参与天选抽奖

> https://api.live.bilibili.com/xlive/lottery-interface/v1/Anchor/Join

*请求方式：POST*

认证方式：Cookie（SESSDATA）

鉴权方式：Cookie中`bili_jct`的值正确并与`csrf`相同

参与直播间天选时刻抽奖；需要携带 Cookie `buvid3`

**正文参数 (application/x-www-form-urlencoded)：**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| room_id | num | 直播间id | 必要 | |
| id | num | 天选抽奖id | 必要 | |
| platform | str | 平台 | 必要 | 固定为 `pc` |
| csrf | str | CSRF Token（位于cookie） | 必要 | |
| gift_id | num | 礼物id | 非必要 | 弹幕抽奖需要赠送指定礼物时使用 |
| gift_num | num | 礼物数量 | 非必要 | 弹幕抽奖需要赠送指定礼物时使用 |

**json回复：**

根对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| code | num | 返回值 | 0：成功 |
| message | str | 错误信息 | |
| data | obj | 信息本体 | 响应结构待补充 |

**示例：**

参与直播间 `22637261` 的 `id=xxx` 天选抽奖

```shell
curl 'https://api.live.bilibili.com/xlive/lottery-interface/v1/Anchor/Join' \
  -b 'SESSDATA=xxx;bili_jct=xxx;buvid3=xxx' \
  --data-urlencode 'room_id=22637261' \
  --data-urlencode 'id=xxx' \
  --data-urlencode 'platform=pc' \
  --data-urlencode 'csrf=xxx'
```

---

## 查询高能榜贡献_app端

> https://api.live.bilibili.com/xlive/general-interface/v1/rank/queryContributionRank

*请求方式：GET*

鉴权方式：APP（access_key）

需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数：**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |
| room_id | num | 直播间id | 必要 | |
| ruid | num | 主播用户mid | 必要 | |
| type | str | 榜单类型 | 必要 | 目前仅发现为 `online_rank` |
| switch | str | 榜单开关类型 | 必要 | 目前仅发现为 `contribution_rank` |

**json回复：**

根对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| code | num | 返回值 | 0：成功 |
| message | str | 错误信息 | |
| data | obj | 信息本体 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| item | array | 高能用户贡献榜列表 | |

`data.item`数组中的对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| rank | num | 排名 | |
| uid | num | 用户mid | |
| uname | str | 用户名 | |
| name | str | 用户名 | 与 `uname` 相同 |
| face | str | 用户头像url | |
| score | num | 贡献值 | |
| medal_name | str | 粉丝勋章名 | 佩戴粉丝勋章时存在 |
| level | str | 勋章等级？ | 作用尚不明确 |
| color | str | 勋章颜色？ | 作用尚不明确 |

**示例：**

查询直播间 `22637261` 的高能用户贡献榜

```shell
curl -G 'https://api.live.bilibili.com/xlive/general-interface/v1/rank/queryContributionRank' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'room_id=22637261' \
  --data-urlencode 'ruid=xxx' \
  --data-urlencode 'type=online_rank' \
  --data-urlencode 'switch=contribution_rank' \
  --data-urlencode 'sign=xxx'
```

---

## 获取房间勋章排名_app端

> https://api.live.bilibili.com/rankdb/v2/RoomRank/mobileMedalRank

*请求方式：GET*

鉴权方式：APP（access_key）

获取直播间粉丝榜（粉丝勋章排名），需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数：**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |
| page | num | 页码 | 必要 | 默认为 `1` |
| roomid | num | 直播间id | 必要 | |
| ruid | num | 主播用户mid | 必要 | |

**json回复：**

根对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| code | num | 返回值 | 0：成功 |
| message | str | 错误信息 | |
| data | obj | 信息本体 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| list | array | 粉丝榜列表 | |
| total_page | num | 总页数 | |

`data.list`数组中的对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| rank | num | 排名 | |
| uid | num | 用户mid | |
| uname | str | 用户名 | |
| name | str | 用户名 | 与 `uname` 相同 |
| face | str | 用户头像url | |
| score | num | 亲密度（勋章积分） | |
| medal_name | str | 粉丝勋章名 | |
| level | str | 勋章等级？ | 作用尚不明确 |
| color | str | 勋章颜色？ | 作用尚不明确 |

**示例：**

查询直播间 `22637261` 第 `1` 页的粉丝榜

```shell
curl -G 'https://api.live.bilibili.com/rankdb/v2/RoomRank/mobileMedalRank' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'page=1' \
  --data-urlencode 'roomid=22637261' \
  --data-urlencode 'ruid=xxx' \
  --data-urlencode 'sign=xxx'
```

---

## 获取用户直播名片_app端

> https://api.live.bilibili.com/live_user/v1/card/card_up

*请求方式：GET*

鉴权方式：APP（access_key）

需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数：**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |
| uid | num | 目标用户mid | 必要 | |

**json回复：**

根对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| code | num | 返回值 | 0：成功 |
| message | str | 错误信息 | |
| data | obj | 主打名片信息 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| uid | num | 主播mid | |
| uname | str | 主播用户名 | |
| face | str | 主播头像url | |
| verify_type | num | 认证类型 | -1：无<br />0：个人认证<br />1：机构认证 |
| desc | str | 认证信息 | |
| level | num | 直播等级 | |
| level_color | num | 等级颜色 | |
| main_vip | num | 是否大会员 | |
| uname_color | num | 用户名颜色 | |
| room_id | num | 直播间id | |
| area_name | str | 直播分区名 | |
| pendant | str | 直播间头像框url | |
| pendant_from | num | （？） | 作用尚不明确 |
| glory_info | array | 荣誉信息列表 | |
| pk_info | array | 赛季信息列表 | |
| season_info_url | str | 赛季信息页面url | |
| follow_num | num | 粉丝数 | |
| is_fans | bool | 当前用户是否为其粉丝 | |
| relation_status | num | 与当前用户的关系 | 大于 `1` 表示已关注 |

`glory_info`数组中的对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| gid | str | 荣誉id | |
| name | str | 荣誉名称 | |
| activity_name | str | 活动名称 | |
| activity_date | str | 活动日期 | |
| pic_url | str | 荣誉图片url | |
| jump_url | str | 跳转链接 | |

`pk_info`数组中的对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| season_id | num | 赛季id | |
| season_name | str | 赛季名称 | |
| season_date_start | str | 赛季开始日期 | |
| season_date_end | str | 赛季结束日期 | |
| pk_rank_name | str | 赛季排名名称 | |
| first_pic_url | str | 赛季图片url | |
| pk_rank_star | num | 赛季星级 | |
| second_rank_icon | str | 排名图标url | |
| rank_info_url_app | str | 排名详情页url | |

**示例：**

查询 `mid=672328094` 的用户直播名片

```shell
curl -G 'https://api.live.bilibili.com/live_user/v1/card/card_up' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'uid=672328094' \
  --data-urlencode 'sign=xxx'
```

---

## 获取SuperChat醒目留言列表_app端

> https://api.live.bilibili.com/av/v1/SuperChat/getMessageList

*请求方式：GET*

鉴权方式：APP（access_key）

需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数：**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |
| room_id | num | 直播间id | 必要 | |

**json回复：**

根对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| code | num | 返回值 | 0：成功 |
| message | str | 错误信息 | |
| data | obj | 信息本体 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| list | array | 醒目留言列表 | |

`data.list`数组中的对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| id | num | 醒目留言id | |
| uid | num | 发送者用户mid | |
| background_image | str | 背景图片url | |
| background_color | str | 背景颜色 | |
| background_icon | str | 背景图标url | |
| background_bottom_color | str | 底部背景颜色 | |
| background_price_color | str | 价格背景颜色 | |
| font_color | str | 字体颜色 | |
| price | num | 留言金额 | 单位：元 |
| rate | num | 汇率？ | 作用尚不明确 |
| time | num | 剩余展示时间 | 单位：秒 |
| start_time | num | 开始展示时间 | 相对开播的秒数？ |
| end_time | num | 结束展示时间 | 相对开播的秒数？ |
| message | str | 留言内容 | |
| trans_mark | num | 是否有翻译 | 0：无<br />1：有 |
| message_trans | str | 翻译后的留言内容 | |
| ts | num | 发送时间 | Unix 秒时间戳 |
| token | str | （？） | 作用尚不明确 |
| user_info | obj | 发送者信息 | |

`user_info`对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| uname | str | 发送者用户名 | |
| face | str | 发送者头像url | |
| face_frame | str | 发送者头像框url | |
| guard_level | num | 大航海等级 | 0：无<br />1：总督<br />2：提督<br />3：舰长 |
| user_level | num | 用户等级 | |
| is_vip | num | 是否vip | |
| is_svip | num | 是否svip | |
| is_main_vip | num | 是否大会员 | |

**示例：**

查询直播间 `22637261` 的醒目留言列表

```shell
curl -G 'https://api.live.bilibili.com/av/v1/SuperChat/getMessageList' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'room_id=22637261' \
  --data-urlencode 'sign=xxx'
```

---

## 查询直播钱包_app端

> https://api.live.bilibili.com/pay/v2/Pay/myWallet

*请求方式：GET*

鉴权方式：APP（access_key）

需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数：**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |

**json回复：**

根对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| code | num | 返回值 | 0：成功 |
| message | str | 错误信息 | |
| data | obj | 钱包信息 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ------ | ---- | ---- | ---- |
| gold | num | 金瓜子余额 | |
| silver | num | 银瓜子余额 | |

**示例：**

```shell
curl -G 'https://api.live.bilibili.com/pay/v2/Pay/myWallet' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'sign=xxx'
```
