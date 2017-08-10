## 播放页信息主动上报

可通过播放器嵌入代码获取页面信息数据，进行部分功能，如：活动开始时间显示、倒计时、结束时间、推流状态、活动状态等自主功能开发。

嵌入页面检测到数据变更时，主动上报发送消息。

### 响应参数

| 参数           | 参数类型     | 参数说明                                     |
| ------------ | -------- | ---------------------------------------- |
| changedParam | array    | 本次更新的字段                                  |
| startedAt    | datetime | 活动开始时间                                   |
| endedAt      | datetime | 活动结束时间                                   |
| isPushing    | boolean  | 是否在推流                                    |
| online       | integer  | pv                                       |
| liveStatus   | enum     | 当前状态，取值：`未开始`、`直播中`、`已结束`                |
| liveType     | enum     | 播放类型，取值：`live` 直播、 `isPrologue`预设视频、`isEpilogue`回放视频 |

### 响应样例
```js
{
  "changedParam": ["isPushing", "startedAt"],
  "startedAt": "2017-07-10T09:44:59.000Z",
  "endedAt": "2017-07-10T12:44:59.000Z",
  "isPushing": true,
  "online": 10,
  "liveStatus": "直播中",
  "liveType": "live"
}
```

### 使用方法

```js
<script>
function receiveMessage(event)
	{
 		if (event.origin.indexOf('shangzhibo.tv') === -1) {
    		return;
		}
		// your code with event.data
	}
	window.onload = function() {
		if (window.addEventListener) {
			window.addEventListener('message', receiveMessage, false);
		} else {
			window.attachEvent('message', receiveMessage);
		}
	}
</script>
```

将上述代码嵌入页面中即可，如有其他数据需要获取可联系杨经理（18968187008）。