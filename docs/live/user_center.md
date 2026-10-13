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

## 获取用户直播信息

> https://api.live.bilibili.com/xlive/web-ucenter/user/live_info

*请求方式: GET*

认证方式：Cookie

主播个人中心首页展示的综合信息

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
| room_id | num | 直播间长ID | |
| main_site_level_rank | num | 主站等级排名 | |
| master | obj | 主播等级信息 | |
| vip_info | obj | 直播舱等红单信息 | |
| live_time | num | 直播时长 | 分钟 |
| bili_coins | num | B币 | |
| san | num | SAN值 | 主播信用分 |
| count | obj | 各类数量统计 | |
| anchor_switch_info | obj | 主播开关信息 | |
| need_guide | num | 是否需要引导 | |
| emoticon_management | num | 表情管理 | |
| up_emoticon_jurisdiction | num | UP主表情权限 | |
| anchor_room_emoticon | num | 直播间表情 | |
| anchor_violations_record | num | 主播违规记录入口 | 1: 显示 |

`data.master`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| level | num | 主播等级 | |
| current | num | 当前经验 | |
| next | num | 下一级所需经验 | |
| medal | null | 勋章 | |

`data.vip_info`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| vip_endtime | str | 舰员到期时间 | `yyyy-MM-dd HH:mm:ss` |
| svip_endtime | str | 提督到期时间 | `yyyy-MM-dd HH:mm:ss` |
| month_price | num | 月费价格 | 单位为金瓜子/1000 |
| year_price | num | 年费价格 | 单位为金瓜子/1000 |
| vip_view_status | bool | 是否展示 | |

`data.count`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| guard | num | 大航海人数 | |
| fans_medal | num | 粉丝勋章人数 | |
| title | num | 头衔数 | |
| title_new | num | 新头衔数 | |
| achieve | num | 成就数 | |

## 获取全局弹幕屏蔽信息

> https://api.live.bilibili.com/xlive/web-ucenter/v1/banned/GetShieldInfo

*请求方式: GET*

认证方式：Cookie

获取主播个人中心设置的全局弹幕屏蔽（区别于直播间维度的`banned_service/v1/shield/get_shield_info`）

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
| shield_user_list | array | 屏蔽用户列表 | |
| keyword_list | array | 屏蔽关键词列表 | str数组 |
| shield_rules | obj | 屏蔽规则 | |

`data.shield_rules`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| rank | num | 屏蔽等级低于 | 0为不屏蔽 |
| verify | num | 屏蔽未认证用户 | 0为不屏蔽 |
| level | num | 屏蔽等级低于 | 0为不屏蔽 |

`data.shield_user_list`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| uid | num | 用户mid | |
| uname | str | 用户名 | |

## 查询主播任务红点状态

> https://api.live.bilibili.com/xlive/web-ucenter/v1/anchorTask/isViewed

*请求方式: GET*

认证方式：Cookie

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
| task_should_notice | num | 任务红点 | 1: 显示 |
| show_reward_entry | num | 奖励入口 | 1: 显示 |
| reward_should_notice | num | 奖励红点 | 1: 显示 |
| task_status | num | 任务状态 | 未知 |
| is_blacked | num | 是否黑名单 | |
| url | str | 奖励页面url | |

## 获取权益中心面板

> https://api.live.bilibili.com/xlive/web-ucenter/v1/privilegeCenter/panel

*请求方式: GET*

认证方式：Cookie

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ---- | ---- | ---- | ------ | ---- |
| source | num | 来源 | 非必要 | `2` |

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
| tab_list | array | 权益tab列表 | |
| pc_tab_list | array | PC端权益tab列表 | 结构同`tab_list` |

`data.tab_list`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| tab_name | str | tab名称 | 如`大航海` |
| tab_type | num | tab类型 | |
| total_num | num | 数量 | |
| alarm_num | num | 红点数 | |

## 获取主播视频权益

> https://api.live.bilibili.com/xlive/app-blink/v1/anchorVideo/GetUserRight

*请求方式: GET*

认证方式：Cookie

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
| state | num | 状态 | 1: 开通 |
| show_dot | num | 红点 | -1: 不显示 |
| is_open | num | 是否开启 | 1: 开启 |
| is_replay_edit_open | bool | 回放剪辑是否开启 | |

## 获取主播开播授权信息

> https://api.live.bilibili.com/xlive/app-blink/v1/anchorVideo/GetAnchorAuthorizationInfo

*请求方式: GET*

认证方式：Cookie

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
| has_reserve_permission | num | 是否有预约权限 | |
| has_live_cut_permission | num | 是否有直播剪辑权限 | |
| has_replay_cut_permission | num | 是否有回放剪辑权限 | |
| allow | num | 是否允许开播 | |
| allow_type | num | 不允许开播原因类型 | 未知 |
| is_allow_fans_level | num | 是否开启粉丝等级限制 | |
| allow_fans_level | num | 粉丝等级限制值 | |
| allow_white_list | num | 是否白名单 | |
| is_same | bool | 未知 | |
| is_show | num | 是否展示 | 1: 展示 |

## 获取推广开关

> https://api.live.bilibili.com/xlive/app-blink/v1/index/getSpreadSwitch

*请求方式: GET*

认证方式：Cookie

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
| spread_switch | bool | 推广开关状态 | |
| url | str | 推广页面url | |
| pc_url | str | PC端推广页面url | |
| alarm_num | num | 红点数 | |

## 获取新版UI开关

> https://api.live.bilibili.com/xlive/app-blink/v1/switch/GetNewUISwitch

*请求方式: GET*

认证方式：Cookie

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
| switch | bool | 新版UI开关状态 | |

## 获取抽奖入口配置

> https://api.live.bilibili.com/xlive/lottery-interface/v1/lottery/getLotteryEntranceConf

*请求方式: GET*

认证方式：Cookie

主播个人中心的抽奖(奖品仓库)入口配置

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
| is_show | bool | 是否展示入口 | |
| jump_to | str | 跳转url | |
| btn_text | str | 按钮文案 | |

## 获取主播抽奖记录

> https://api.live.bilibili.com/xlive/lottery-interface/v1/Anchor/Record

*请求方式: GET*

认证方式：Cookie

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ---- | ---- | ---- | ------ | ---- |
| page | num | 页码 | 必要 | 从1开始 |

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
| list | array | 抽奖记录列表 | 无记录时为空 |
| total_count | num | 总数 | |
| page_count | num | 总页数 | |

## 查询是否有主播抽奖

> https://api.live.bilibili.com/xlive/lottery-interface/v1/anchor/HasAnchorLottery

*请求方式: GET*

认证方式：Cookie

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
| has | bool | 是否有进行中的主播抽奖 | |
| business_icon | str | 业务图标 | |
| business_name | str | 业务名称 | |
| activity_url | str | 活动url | |
| pc_activity_url | str | PC端活动url | |
| newly_opened | bool | 是否新开 | |
| has_auth | bool | 是否有权限 | |

## 查询税务信息灰度

> https://api.live.bilibili.com/xlive/revenue/v3/anchorAccount/getTaxIncomeGrey

*请求方式: GET*

认证方式：Cookie

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
| in_grey | num | 是否在灰度内 | 1: 在灰度内 |

## 获取大航海权益配置

> https://api.live.bilibili.com/xlive/general-interface/v1/guardBenefit/Config

*请求方式: GET*

认证方式：Cookie

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
| have_custom_tab | bool | 是否有自定义tab | |
| num | num | 数量 | |
| duration | num | 时长 | |
| show_check | bool | 是否展示检查 | |
| check_condition | obj | 检查条件 | |

`data.check_condition`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| anchor_legal | bool | 主播合规 | |
| guard_num | bool | 大航海数量达标 | |

## 获取主播大航海权益列表

> https://api.live.bilibili.com/xlive/general-interface/v1/guardBenefit/ListByAnchor

*请求方式: GET*

认证方式：Cookie

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ---- | ---- | ---- | ------ | ---- |
| page | num | 页码 | 必要 | 从1开始 |
| type | num | 类型 | 必要 | `3` |

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
| count | num | 总数 | |
| page_count | num | 总页数 | |
| list | array | 权益列表 | 无数据时为null |

## 查询大航海权益入口红点

> https://api.live.bilibili.com/xlive/general-interface/v1/guardBenefit/EntranceAdd

*请求方式: GET*

认证方式：Cookie

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
| have | bool | 是否有红点 | |

## 获取大航海配置开关

> https://api.live.bilibili.com/xlive/guard-interface/general/abs

*请求方式: GET*

认证方式：Cookie

按场景查询大航海相关功能开关

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ---- | ---- | ---- | ------ | ---- |
| scenes | str | 场景列表 | 必要 | 如`guard_renew_advance`(大航海提前续费) |
| web_location | str | Web位置 | 非必要 | |

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
| val | obj | 各场景开关值 | 键为场景名, 值为开关值 |

## 获取荣誉头衔说明

> https://api.live.bilibili.com/xlive/app-ucenter/v2/title/GetHonorDescription

*请求方式: GET*

认证方式：Cookie

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
| username | str | 用户名 | |
| next_glory_desc | str | 下一荣誉描述 | |
| have_glory_title | obj | 当前荣誉头衔 | |
| have_glory_desc | str | 当前荣誉描述 | |
| unlock | array | 已解锁列表 | |
| lock | array | 未解锁列表 | |
| consume | num | 当前消耗 | |
| next_glory_consume | num | 下一级消耗 | |
| royal_url | str | 贵族中心url | |
| gear_id | num | 档位ID | |
| br_status | num | 未知 | |
| br_jump_url | str | 跳转url | |

`data.have_glory_title`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| tid | num | 头衔ID | |
| name | str | 头衔名称 | |
| web_dynamic_url_webp | str | 动效图片url(webp) | |
| web_dynamic_url_apng | str | 动效图片url(apng) | |
| web_static_pic | str | 静态图片url | |

## 获取主播申请信息

> https://api.live.bilibili.com/live_user/v1/AnchorApply/info

*请求方式: GET*

认证方式：Cookie

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功<br />4: 你没有权限 |
| message | str | 错误信息 | `success` |
| data | obj | 信息本体 | |

`data`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| show_apply_history | bool | 是否展示申请历史 | |
| can_apply | bool | 是否可以提交申请 | |
| reason_type | num | 不可申请原因类型 | 0: 无 |
| reason_message | str | 不可申请原因文案 | |

## 获取官方认证信息

> https://api.live.bilibili.com/live_user/v1/Official/display

*请求方式: GET*

认证方式：Cookie

需要相应权限（如签约主播）, 无权限时返回`code=4`

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功<br />4: 你没有权限 |
| message | str | 错误信息 | |
| data | array | 信息本体 | 无权限时为空 |

## 获取个人中心展示信息

> https://api.live.bilibili.com/live_user/v1/UserCenter/getShowInfo

*请求方式: GET*

认证方式：Cookie

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
| show_guild_menu | bool | 是否展示公会菜单 | |
| show_my_guild_menu | bool | 是否展示我的公会菜单 | |
| is_guild_master | bool | 是否公会会长 | |
| sign_anchor | obj | 签约主播信息 | |
| official_anchor | obj | 官方认证主播信息 | |
| mission_tab | obj | 任务tab信息 | |

`data.sign_anchor`、`data.official_anchor`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| status | num | 状态 | 0: 无 |
| start_date | str | 开始日期 | |
| end_date | str | 结束日期 | |

`data.mission_tab`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| type | num | 类型 | |
| show_tab | bool | 是否展示 | |
