# 电竞信息

## 获取电竞赛事列表

> https://api.bilibili.com/x/esports/component/contests

*请求方式: GET*

认证方式：无（无需Cookie）

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| sid | num | 赛事ID | 必要 | |
| division | str | 分区 | 非必要 | 空字符串为全部 |

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
| history | array | 已结束赛事列表 | |
| future | array | 即将开始赛事列表 | |
| prev | num | 上一页标识 | 未知 |
| next | num | 下一页标识 | 未知 |

`data.history`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 赛事ID | |
| start_time | num | 开始时间 | 10位Unix时间戳 |
| end_time | num | 结束时间 | 10位Unix时间戳 |
| title | str | 赛事标题 | |
| status | str | 赛事状态 | 未知 |
| collection_url | str | 收藏页面URL | |
| live_room | num | 直播间ID | |
| play_back | str | 回放URL | |
| data_type | num | 数据类型 | 未知 |
| match_id | num | 比赛ID | |
| season_id | num | 赛季ID | |
| guess_type | num | 竞猜类型 | 未知 |
| series_id | num | 赛系列ID | |
| is_sub | num | 是否订阅 | 未知 |
| is_guess | num | 是否可竞猜 | 未知 |
| home | obj | 主队信息 | |
| away | obj | 客队信息 | |
| series | null | 赛系信息 | |
| contest_status | num | 赛事状态 | 未知 |
| contest_freeze | num | 赛事冻结状态 | 未知 |
| game_state | num | 游戏状态 | 未知 |
| guess_show | num | 竞猜显示 | 未知 |
| home_score | num | 主队得分 | |
| away_score | num | 客队得分 | |
| game_stage | str | 游戏阶段 | |
| season_title | str | 赛季标题 | |
| season_type | num | 赛季类型 | 未知 |
| teams | array | 参赛队伍列表 | |
| hottest_player | obj | 最热选手信息 | |

`data.history[].home`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| (未知) | | | 子对象字段未展开 |

`data.history[].away`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| (未知) | | | 子对象字段未展开 |

`data.history[].hottest_player`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| (未知) | | | 子对象字段未展开 |

## 获取赛季队伍列表

> https://api.bilibili.com/x/esports/component/season/teams

*请求方式: GET*

认证方式：无（无需Cookie）

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| sid | num | 赛季ID | 必要 | |

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
| season | obj | 赛季信息 | |
| teams | array | 队伍列表 | |

`data.season`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 赛季ID | |
| title | str | 赛季标题 | |
| sub_title | str | 赛季副标题 | |
| logo | str | 赛季logo路径 | |
| leida_sid | num | 雷达(数据源)赛事ID | |

`data.teams`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| team_id | num | 队伍ID | |
| team_title | str | 队伍简称 | |
| region_id | num | 赛区ID | |
| season_id | num | 赛季ID | |
| rank | num | 排名 | |
| logo | str | 队伍logo路径 | |
| uid | num | 队伍关联用户mid | |
| leida_id | num | 雷达(数据源)队伍ID | |
| logo_full | str | 队伍logo完整url | |

## 获取队伍赛程列表

> https://api.bilibili.com/x/esports/component/v2/teams/contests

*请求方式: GET*

认证方式：无（无需Cookie）

按队伍查询其已结束与未开始的比赛

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| sid | num | 赛季ID | 必要 | |
| series_id | num | 赛系列ID | 必要 | |
| team_ids | str | 队伍ID列表 | 必要 | 使用英文逗号分隔 |
| group_name | str | 分组名称 | 非必要 | 如`登峰组` |
| ps | num | 每页项数 | 非必要 | |

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
| history | array | 已结束赛事列表 | 字段同[获取电竞赛事列表](#获取电竞赛事列表)中`data.history`数组中的对象 |
| future | array | 即将开始赛事列表 | 同上 |
| prev | num | 上一页标识 | 未知 |
| next | num | 下一页标识 | 未知 |

`data.history[].home`、`data.history[].away`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 队伍ID | |
| icon | str | 队伍logo路径 | |
| name | str | 队伍简称 | |
| wins | num | 胜场数 | |
| region | str | 赛区名称 | |
| region_id | num | 赛区ID | |
| ExternalTeamId | num | 外部队伍ID | |
| division_name | str | 赛区分区名 | 如`lpl` |
| division_logo | str | 赛区分区logo路径 | |
| player_grade_detail | null | 选手评分详情 | |
| is_success_team | bool | 是否获胜队伍 | |

## 获取赛系列积分榜

> https://api.bilibili.com/x/esports/season/series/point_match

*请求方式: GET*

认证方式：无（无需Cookie）

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| series_id | num | 赛系列ID | 必要 | |

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
| season_id | num | 赛季ID | |
| series_id | num | 赛系列ID | |
| use_team_group | bool | 是否按分组展示 | |
| use_small_score | bool | 是否使用小分 | |
| total_teams | null | 全部队伍 | |
| group_teams | array | 分组队伍列表 | `use_team_group`为`true`时有效 |
| refresh_time | num | 数据刷新时间 | 10位Unix时间戳 |
| group_outlet_num | num | 分组出线名额 | |
| is_dogfall_match | bool | 是否允许平局 | |
| teams | null | 队伍列表 | |
| season | obj | 赛季信息 | |

`data.season`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 赛季ID | |
| leida_sid | num | 雷达(数据源)赛事ID | |
| stime | num | 开始时间 | 10位Unix时间戳 |
| etime | num | 结束时间 | 10位Unix时间戳 |
| title | str | 赛季标题 | |
| season_type | num | 赛季类型 | 未知 |

`data.group_teams`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| name | str | 分组名称 | 如`登峰组` |
| teams | array | 分组内队伍积分列表 | |

`data.group_teams[].teams`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| team_id | num | 队伍ID | |
| group_name | str | 分组名称 | |
| team_name | str | 队伍简称 | |
| icon_url | str | 队伍logo路径 | |
| win_times | num | 胜场数 | |
| lose_times | num | 负场数 | |
| tie_times | num | 平局数 | |
| score | num | 积分 | |
| small_score | num | 小分净胜 | |
| rank | num | 分组内排名 | |
| leida_tid | num | 雷达(数据源)队伍ID | |
| region_id | num | 赛区ID | |
| division_name | str | 赛区分区名 | 如`lpl` |
| division_logo | str | 赛区分区logo路径 | |
| win_small_score | num | 胜小分 | |
| lose_small_score | num | 负小分 | |
| tie_small_score | num | 平小分 | |

## 获取战队详情

> https://api.bilibili.com/x/esports/special/team

*请求方式: GET*

认证方式：无（无需Cookie）

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| tp | num | 类型 | 必要 | `1` |
| leida_sid | num | 雷达(数据源)赛事ID | 必要 | |
| id | num | 雷达(数据源)队伍ID | 必要 | |

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
| team | obj | 战队基本信息 | |
| stats | obj | 战队数据统计 | |
| recent | obj | 近期比赛 | 未知 |
| gid | num | 未知 | |

`data.team`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 队伍ID | |
| title | str | 队伍简称 | |
| sub_title | str | 队伍副标题 | |
| e_title | str | 队伍英文标题 | |
| create_time | num | 创建时间 | 10位Unix时间戳 |
| area | str | 地区 | |
| logo | str | 队伍logo路径 | |
| uid | num | 队伍关联用户mid | |
| members | str | 成员 | |
| dic | str | 未知 | |
| is_deleted | num | 是否删除 | |
| video_url | str | 相关视频url | |
| profile | str | 战队简介 | |
| leida_tid | num | 雷达(数据源)队伍ID | |
| reply_id | num | 评论区ID | |
| team_type | num | 队伍类型 | 未知 |
| region_id | num | 赛区ID | |
| division_name | str | 赛区分区名 | |
| division_logo | str | 赛区分区logo路径 | |

`data.stats`对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 数据ID | |
| team_id | num | 雷达(数据源)队伍ID | |
| acronym | str | 队伍缩写 | |
| leida_sid | num | 雷达(数据源)赛事ID | |
| name | str | 战队全名 | |
| image_url | str | 战队图片url | |
| win | num | 胜率 | 0~1 |
| kda | num | 场均KDA | |
| kills | num | 场均击杀 | |
| deaths | num | 场均死亡 | |
| assists | num | 场均助攻 | |
| tower_kills | num | 场均推塔 | |
| total_minions_killed | num | 场均补刀 | |
| first_tower | num | 一塔率 | 0~1 |
| first_inhibitor | num | 一水晶率 | 0~1 |
| first_dragon | num | 一小龙率 | 0~1 |
| first_baron | num | 一男爵率 | 0~1 |
| first_blood | num | 一血率 | 0~1 |
| wards_placed | num | 场均插眼 | |
| inhibitor_kills | num | 场均水晶 | |
| baron_kills | num | 场均男爵 | |
| gold_earned | num | 场均经济 | |
| games_count | num | 比赛场次 | |
| players | array | 选手列表 | |
| ctime | str | 数据创建时间 | ISO 8601 |
| mtime | str | 数据更新时间 | ISO 8601 |
| baron_rate | num | 男爵率 | 百分数 |
| dragon_rate | num | 小龙率 | 百分数 |
| hits | num | 场均伤害 | |
| lose_num | num | 负场数 | |
| money | num | 场均经济(千) | |
| total_damage | num | 场均总伤害(千) | |
| win_num | num | 胜场数 | |
| image_thumb | str | 战队缩略图url | |
| new_data | num | 未知 | |

`data.stats.players`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| name | str | 选手ID | |
| image_url | str | 选手头像url | |
| id | num | 选手ID(数字) | |
| role | str | 位置代码 | `1`: ADC<br/>`2`: 中单<br/>`3`: 上单<br/>`4`: 打野<br/>`5`: 辅助 |

## 获取英雄排行榜

> https://api.bilibili.com/x/esports/stats/hero2/rank

*请求方式: GET*

认证方式：无（无需Cookie）

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| top | num | 返回项数 | 必要 | |
| season_id | num | 赛季ID | 必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| ttl | num | 未知 | |
| data | array | 英雄榜数据列表 | |

`data`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 数据ID | |
| tournament_id | num | 雷达(数据源)赛事ID | |
| hero_id | num | 英雄ID | |
| hero_name | str | 英雄名称 | |
| hero_image | str | 英雄头像url | |
| appear_count | num | 出场次数 | |
| prohibit_count | num | 被禁用次数 | |
| victory_count | num | 获胜次数 | |
| game_count | num | 总局数 | |
| victory_rate | num | 胜率 | 0~1 |

## 获取选手MVP榜

> https://api.bilibili.com/x/esports/stats/player/mvp/rank

*请求方式: GET*

认证方式：无（无需Cookie）

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| top | num | 返回项数 | 必要 | |
| season_id | num | 赛季ID | 必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| ttl | num | 未知 | |
| data | array | 选手MVP榜数据列表 | |

`data`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 选手ID | |
| player_id | num | 选手ID | |
| player_name | str | 选手ID(名称) | |
| image_url | str | 选手头像url | |
| team_id | num | 所属队伍ID | |
| team_name | str | 所属队伍简称 | |
| position_id | num | 位置代码 | `1`: ADC<br/>`2`: 中单<br/>`3`: 上单<br/>`4`: 打野<br/>`5`: 辅助 |
| position | str | 位置名称 | 如`打野` |
| Mvp | num | MVP次数 | |
| rank | num | 排名 | |

## 获取选手KDA榜

> https://api.bilibili.com/x/esports/stats/player/kda/rank

*请求方式: GET*

认证方式：无（无需Cookie）

**URL参数:**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------ | ---- | ---- | ------ | ---- |
| top | num | 返回项数 | 必要 | |
| season_id | num | 赛季ID | 必要 | |

**JSON回复:**

根对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| code | num | 返回值 | 0: 成功 |
| message | str | 错误信息 | |
| ttl | num | 未知 | |
| data | array | 选手KDA榜数据列表 | |

`data`数组中的对象:

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| id | num | 选手ID | |
| player_id | num | 选手ID | |
| player_name | str | 选手ID(名称) | |
| image_url | str | 选手头像url | |
| team_id | num | 所属队伍ID | |
| team_name | str | 所属队伍简称 | |
| position_id | num | 位置代码 | `1`: ADC<br/>`2`: 中单<br/>`3`: 上单<br/>`4`: 打野<br/>`5`: 辅助 |
| position | str | 位置名称 | 如`ADC` |
| Kda | num | KDA数值 | |
