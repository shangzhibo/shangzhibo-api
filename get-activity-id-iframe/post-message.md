# 播放页信息主动上报

可通过播放器嵌入代码获取页面信息数据，进行部分功能，如：活动开始时间显示、倒计时、结束时间、推流状态、活动状态等自主功能开发。

嵌入页面检测到数据变更时，主动上报发送消息。

## 响应参数

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| type | enum | 消息类型，取值：`ping` 直播实时信息、 `comment` 评论 |
| data | object | 消息内容 |

### data when type is ping

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| changedParam | array | 本次更新的字段 |
| startedAt | datetime | 活动开始时间 |
| endedAt | datetime | 活动结束时间 |
| isPushing | boolean | 是否在推流 |
| online | integer | pv |
| liveStatus | enum | 当前状态，取值：`未开始`、`直播中`、`已结束` |
| liveType | enum | 播放类型，取值：`live` 直播、 `isPrologue`预设视频、`isEpilogue`回放视频 |

### 响应样例

```javascript
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

### data when type is comment

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | integer | 评论 ID |
| status | enum | 评论状态，取值：`pending` 待审核、 `passed`已通过、`failed`禁用 |
| content | string | 评论内容 |
| createdAt | string | 创建时间 |
| updatedAt | string | 更新时间 |
| activityId | string | 活动 ID |
| user | object | 用户信息 |

### 用户信息

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| role | enum | 角色，取值：`agent` 管理员、 `user`登录用户、`anonymous`匿名用户 |
| nickname | string | 用户名 |
| avatar | string | 用户头像 |

### 响应样例

```javascript
{
    "id": 42,
    "user": {
        "role": "agent",
        "nickname": "stringValue",
        "avatar": "stringValue"
    },
    "activityId": "stringValue",
    "status": "pending",
    "content": "stringValue",
    "createdAt": "stringValue",
    "updatedAt": "stringValue"
}
```

## 使用方法

```javascript
<script>
(function() {
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
})()
</script>
```

将上述代码嵌入页面中即可，如有其他数据需要获取可联系杨经理（18968187008）。

