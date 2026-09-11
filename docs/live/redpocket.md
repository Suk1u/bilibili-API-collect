# 直播间人气红包

## 获取指定直播间的红包信息

> https://api.live.bilibili.com/xlive/lottery-interface/v1/lottery/getLotteryInfoWeb

*请求方式：GET*

认证方式（可选）：Cookie（SESSDATA）

如果不携带Cookie信息，user_status将始终返回2（未参与）。

如果所查询的直播间无红包，popularity_red_pocket为null。

**url参数：**

| 参数名  | 类型 | 内容             | 必要性 | 备注 |
| ------- | ---- | ---------------- | ------ | ---- |
| roomid | str  | 直播间id | 必要   |      |

**json回复：**

根对象：

| 字段    | 类型   | 内容       | 备注          |
| ------- | ------ | ---------- | ------------- |
| code    | num    | 返回值     | 0：成功       |
| message | str    | 错误信息   | 0：成功 |
| ttl    | num | TimeToLive | 正常为1              |
| data | object | 返回数据 |               |

`data`对象：

| 项   | 类型 | 内容        | 备注 |
| ---- | ---- | ----------- | ---- |
| popularity_red_pocket    | array  | 人气红包信息     |      |
| anchor_lottery_info | obj | 主播抽奖信息 |      |
| ……   | ......  | ……          | ……   |

`anchor_lottery_info`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| lot_id | num | 抽奖id | |
| asset_icon | str | 抽奖图标 | |
| jump_url | str | 跳转链接 | |

`popularity_red_pocket`数组中的对象：

| 字段 | 类型 | 内容       | 备注 |
| ---- | ---- | ---------- | ---- |
| lot_id   | num  | 红包id   |      |
| sender_uid | num | 红包发送者uid   |      |
| sender_name | str | 红包发送者昵称 |      |
| sender_face | str | 红包发送者头像 |      |
| join_requirement | num | 参与条件? |      |
| danmu | str | 参与红包时自动发送的弹幕内容 |      |
| awards | array | 红包内容 |      |
| lot_status | num | 未知 | |
| h5_url | str | 红包界面 | |
| user_status | num | 用户是否已参与 | 1：已参与  2：未参与 |
| lot_config_id | num | 未知 | |
| total_price | num | 红包总计价格 | |

**示例：**

查询房间号为24146996的直播间红包信息：

```shell
curl -G 'https://api.live.bilibili.com/xlive/lottery-interface/v1/lottery/getLotteryInfoWeb?roomid=24146996'
```

<details>
<summary>查看响应示例：</summary>

```json

{
	"code": 0,
	"message": "0",
	"ttl": 1,
	"data": {
		"pk": null,
		"guard": null,
		"gift": null,
		"storm": null,
		"silver": null,
		"activity_box": {
			"ACTIVITY_ID": 0,
			"ACTIVITY_PIC": ""
		},
		"danmu": null,
		"anchor": null,
		"red_pocket": null,
		"popularity_red_pocket": [{
			"lot_id": 622474,
			"sender_uid": 1651908873,
			"sender_name": "九泽糖糖の小蘑菇",
			"sender_face": "http://i0.hdslb.com/bfs/face/c932c5c8b1607fe2e1da22b9780af19662dac939.jpg",
			"join_requirement": 1,
			"danmu": "老板大气！点点红包抽礼物！",
			"awards": [{
				"gift_id": 31212,
				"num": 2,
				"gift_name": "打call",
				"gift_pic": "https://s1.hdslb.com/bfs/live/f75291a0e267425c41e1ce31b5ffd6bfedc6f0b6.png"
			}, {
				"gift_id": 31214,
				"num": 3,
				"gift_name": "牛哇",
				"gift_pic": "https://s1.hdslb.com/bfs/live/23475a7a6170e0d94ba52720e23060dc7604b735.png"
			}, {
				"gift_id": 31216,
				"num": 3,
				"gift_name": "i了i了",
				"gift_pic": "https://s1.hdslb.com/bfs/live/1157a445487b39c0b7368d91b22290c60fa665b2.png"
			}],
			"start_time": 1645358104,
			"end_time": 1645358284,
			"last_time": 180,
			"remove_time": 1645358299,
			"replace_time": 1645358294,
			"current_time": 1645358231,
			"lot_status": 1,
			"h5_url": "https://live.bilibili.com/p/html/live-app-red-envelope/popularity.html?is_live_half_webview=1\u0026hybrid_half_ui=1,5,100p,100p,000000,0,50,0,0,1;2,5,100p,100p,000000,0,50,0,0,1;3,5,100p,100p,000000,0,50,0,0,1;4,5,100p,100p,000000,0,50,0,0,1;5,5,100p,100p,000000,0,50,0,0,1;6,5,100p,100p,000000,0,50,0,0,1;7,5,100p,100p,000000,0,50,0,0,1;8,5,100p,100p,000000,0,50,0,0,1\u0026hybrid_rotate_d=1\u0026hybrid_biz=popularityRedPacket\u0026lotteryId=622474",
			"user_status": 1,
			"lot_config_id": 3,
			"total_price": 1600
		}],
		"activity_box_info": null
	}
}
```

</details>

---

## 抢人气红包

> https://api.live.bilibili.com/xlive/lottery-interface/v1/popularityRedPocket/RedPocketDraw

*请求方式：POST*

认证方式：Cookie（SESSDATA）

鉴权方式：Cookie中`bili_jct`的值正确并与`csrf`相同

参与直播间人气红包抽奖

**url参数：**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------- | ---- | ---------------- | ------ | ---- |
| csrf | str | CSRF Token（位于cookie） | 必要 | |

**正文参数 (application/x-www-form-urlencoded)：**

| 参数名 | 类型 | 内容 | 必要性 | 备注 |
| ------- | ---- | ---------------- | ------ | ---- |
| uid | num | 当前用户mid | 必要 | |
| room_id | num | 直播间id | 必要 | |
| ruid | num | 主播用户mid | 必要 | |
| lot_id | num | 红包抽奖id | 必要 | 可通过[获取指定直播间的红包信息](#获取指定直播间的红包信息)获得 |
| ts | num | 当前时间 | 必要 | Unix 秒时间戳 |

**json回复：**

根对象：

| 字段    | 类型   | 内容       | 备注          |
| ------- | ------ | ---------- | ------------- |
| code    | num    | 返回值     | 0：成功       |
| message | str    | 错误信息   | |
| data    | obj | 参与结果 | |

`data`对象：

| 字段 | 类型 | 内容 | 备注 |
| ---- | ---- | ---- | ---- |
| join_status | num | 参与状态 | 1：参与成功 |

注：`data` 中其余字段作用尚不明确，响应结构待补充

**示例：**

参与直播间 `24146996` 的 `lot_id=622474` 人气红包

```shell
curl 'https://api.live.bilibili.com/xlive/lottery-interface/v1/popularityRedPocket/RedPocketDraw?csrf=xxx' \
  -b 'SESSDATA=xxx;bili_jct=xxx' \
  --data-urlencode 'uid=xxx' \
  --data-urlencode 'room_id=24146996' \
  --data-urlencode 'ruid=xxx' \
  --data-urlencode 'lot_id=622474' \
  --data-urlencode 'ts=1234567890'
```
