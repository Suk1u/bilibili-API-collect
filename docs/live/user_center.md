# 直播用户中心相关接口

## 获取用户实验室信息插件

> https://api.live.bilibili.com/xlive/web-ucenter/v1/labs/InfoPlugs

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
| data | obj | 信息本体 | |

---

## 获取直播用户信息

> https://api.live.bilibili.com/xlive/web-ucenter/user/get_user_info

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
| data | obj | 用户信息 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| uid | num | 用户UID | |
| uname | str | 用户名 | |
| face | str | 头像 | |
| level | num | 等级 | |
| level_color | num | 等级颜色 | |
| is_svip | num | 是否SVIP | |
| is_vip | num | 是否VIP | |
| billCoin | num | B币余额 | |
| silver | num | 银瓜子余额 | |
| gold | num | 金瓜子余额 | |
| achieve | obj | 成就信息 | |
| user_level | num | 用户等级 | |
| user_next_level | num | 下一等级 | |
| user_intimacy | num | 当前亲密度 | |
| user_next_intimacy | num | 下一等级所需亲密度 | |
| is_level_top | num | 是否满级 | 0：否<br/>1：是 |
| user_level_rank | str | 等级排名 | |
| user_charged | num | 用户充值状态 | |
| identification | num | 身份标识 | |
| wealth_info | obj | 财富信息 | |

`data.wealth_info`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| level_total_score | num | 等级总积分 | |
| cur_score | num | 当前积分 | |
| upgrade_need_score | num | 升级所需积分 | |
| status | num | 状态 | |
| dm_icon_key | str | 弹幕图标key | |

---

## 获取直播间首页配置

> https://api.live.bilibili.com/xlive/web-ucenter/v1/room/GetHomePageConfig

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
| data | obj | 配置信息 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| dm_tag_info | obj | 弹幕标签信息 | |
| danmu_extra | obj | 弹幕额外配置 | |
| dm_activity | obj | 弹幕活动信息 | |

`data.dm_tag_info`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| dm_tag | num | 弹幕标签 | |
| platform | null | 平台 | |
| extra | str | 额外信息 | |
| dm_chronos_extra | str | 弹幕时间额外信息 | |
| dm_mode | null | 弹幕模式 | |
| dm_chronos_screen_type | num | 弹幕时间屏幕类型 | |
| material_conf | obj | 素材配置 | |

`data.danmu_extra`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| screen_switch_off | bool | 是否关闭屏幕切换 | |
| chronos_kv | str | 时间KV配置 | |

`data.dm_activity`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| activity_list | null | 活动列表 | |
| ts | num | 时间戳 | |

---

## 获取用户头衔

> https://api.live.bilibili.com/xlive/web-ucenter/v1/user_title/GetTitles

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
| data | array | 头衔列表 | |

---

## 获取表情引导

> https://api.live.bilibili.com/xlive/web-ucenter/v1/emoticon/GetEmoticonGuide

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
| data | obj | 表情引导信息 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| is_open_guide | num | 是否开启引导 | 0：关闭<br/>1：开启 |
| guide_duration | num | 引导持续时间 | 单位：秒 |
| guide_emoticon_info | obj | 引导表情信息 | |

---

## 获取Web关注列表

> https://api.live.bilibili.com/xlive/web-ucenter/v1/xfetter/GetWebList

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
| data | obj | 关注列表 | |

---

## 直播签到_app端

> https://api.live.bilibili.com/rc/v1/Sign/doSign

*请求方式: GET*

鉴权方式: APP（access_key）

需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |

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
| text | str | 签到结果文案 | |

注: `data` 中其余字段作用尚不明确，响应结构待补充

**示例:**

```shell
curl -G 'https://api.live.bilibili.com/rc/v1/Sign/doSign' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'sign=xxx'
```

---

## 获取签到信息_app端

> https://api.live.bilibili.com/rc/v2/Sign/getSignInfo

*请求方式: GET*

鉴权方式: APP（access_key）

需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 签到信息 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| is_signed | bool | 今日是否已签到 | |
| days | num | （？） | 作用尚不明确 |
| sign_days | num | 已签到天数 | |
| h5_url | str | 签到页面链接 | |
| days_award | array | 签到奖励列表 | |
| awards | array | 签到奖励列表 | |

`days_award`、`awards`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| count | num | 奖励数量 | |
| award | str | 奖励名称 | |
| text | str | 奖励文案 | |
| img | obj | 奖励图片 | |

`img`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| width | num | 图片宽度 | |
| src | str | 图片链接 | |
| height | num | 图片高度 | |

**示例:**

```shell
curl -G 'https://api.live.bilibili.com/rc/v2/Sign/getSignInfo' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'sign=xxx'
```

---

## 获取主播头衔列表_app端

> https://api.live.bilibili.com/rc/v1/Title/getTitle

*请求方式: GET*

鉴权方式: APP（access_key）

需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | array | 头衔列表 | |

`data`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | str | 头衔id | |
| title | str | 头衔名称 | |
| img | str | 头衔图片url | |

**示例:**

```shell
curl -G 'https://api.live.bilibili.com/rc/v1/Title/getTitle' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'sign=xxx'
```

---

## 获取当前宝箱任务_app端

> https://api.live.bilibili.com/mobile/freeSilverCurrentTask

*请求方式: GET*

鉴权方式: APP（access_key）

用于获取直播观看宝箱（免费瓜子）任务信息，需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 任务信息 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| time_end | num | 宝箱开启时间 | Unix 秒时间戳 |

注: `data` 中其余字段作用尚不明确，响应结构待补充

**示例:**

```shell
curl -G 'https://api.live.bilibili.com/mobile/freeSilverCurrentTask' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'sign=xxx'
```

---

## 领取宝箱瓜子_app端

> https://api.live.bilibili.com/mobile/freeSilverAward

*请求方式: GET*

鉴权方式: APP（access_key）

用于领取直播观看宝箱（免费瓜子）奖励，需要 APP 签名，公共参数（`access_key`、`appkey`、`build`、`mobi_app`、`platform`、`ts`、`sign`）及签名方法见 [APP 签名](../misc/sign/APP.md)，下表仅列出业务参数

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| actionKey | str | 鉴权字段类型 | 必要 | 固定为 `appkey` |

注: 第三方客户端 biliuwp-lite 调用该接口时未携带其他业务参数（宝箱任务时间等由服务端校验）

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| data | obj | 领取结果 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| awardSilver | num | 获得的银瓜子数量 | |

注: `data` 中其余字段作用尚不明确，响应结构待补充

**示例:**

```shell
curl -G 'https://api.live.bilibili.com/mobile/freeSilverAward' \
  --data-urlencode 'access_key=xxx' \
  --data-urlencode 'appkey=xxx' \
  --data-urlencode 'build=xxx' \
  --data-urlencode 'mobi_app=android' \
  --data-urlencode 'platform=android' \
  --data-urlencode 'ts=1234567890' \
  --data-urlencode 'actionKey=appkey' \
  --data-urlencode 'sign=xxx'
```
