## 创建活动

### 接口

创建活动

```js
POST /api/activity
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| --- | --- | --- | --- |
| name | string | 活动名称 | 是 |
| startedAt | datetime | 直播开始时间 | 否 |
| endedAt | datetime | 直播结束时间 | 否 |

#### 请求样例

```js
{
  "name": "哈哈哈",
  "start_time": "2017-08-09 12:00:00",
  "end_time": "2017-08-10 13:00:00"
}
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| id | string | 活动 ID |
| name | string | 活动名称 |
| categoryId | integer | 活动分类 ID |
| status | string | 活动状态，enabled 允许推流 disabled 禁止推流 forbidden 管理员禁止推流 deleted 频道已被删除 |
| agentId | integer | 账号 ID |
| startedAt | string | 活动开始时间 |
| endedAt | string | 活动结束时间 |
| pushDomain | string | 推流域名 |
| pullDomain | string | 拉流域名 |
| isPushing | boolean | 是否在推流 |
| createdAt | string | 活动创建时间 |
| updateAt | string | 活动更新时间 |
| app | string | 应用名称 |
| stream | string | 流名称 |
| isPrologueEnabled | boolean | 是否启用预设视频 |
| isBackupRecordEnabled | boolean | 是否启用备用录播视频 |
| isLiveEnabled | boolean | 是否开启播放页直播 |
| isFakeEnabled | boolean | 是否启用人数放大 |
| fake.baseCount | integer | 基础人数 |
| fake.increaseMin | integer | 每增加一次真实用户访问，观看人数增加的最小值 |
| fake.increaseMax | integer | 每增加一次真实用户访问，观看人数增加的最大值 |
| isFilterAllEnabled | boolean | 是否禁言所有观众 |
| filterIpList | object | 禁言 IP 列表 |
| filterSidList | object | 禁言 Session ID 列表 |
| filterUserList | object | 禁言用户列表 |
| isRobotEnabled | boolean | 是否启用机器人 |
| robot.initialCount | integer | 初始评论数 |
| robot.incrementCount | integer | 每增长 100 个用户 PV 增加的评论数 |
| expired | boolean | 活动是否超过最大推流时长 |
| maxConcurrentUser | integer | 最大并发在线人数，-1 表示不限制最大在线人数 |
| maxPushingTime | integer | 最大推流时长，单位 秒，-1 表示不限制最大推流时长 |

#### 响应样例

```js
{
    "id": "8930091",
    "name": "哈哈哈",
    "categoryId": 1,
    "status": "enabled",
    "agentId": 100020,
    "startedAt": "2017-08-09T09:48:02.000Z",
    "endedAt": "2017-08-10T09:48:02.000Z",
    "pushDomain": "push.shangzhibo.tv",
    "pullDomain": "play.shangzhibo.tv",
    "isPushing": false,
    "createdAt": "2017-08-09T08:48:02.120Z",
    "updatedAt": "2017-08-09T08:48:02.120Z",
    "app": "rJlwCjrdwZ",
    "stream": "rJ-PCsSuD-?auth_key=1533804482-0-0-2a144739ffaad7ef46a34b63fa524491",
    "isPrologueEnabled": true,
    "isEpilogueEnabled": true,
    "isBackupRecordEnabled": false,
    "isLiveEnabled": true,
    "fake": {
        "baseCount": 0,
        "increaseMin": 1,
        "increaseMax": 1
    },
    "isFakeEnabled": false,
    "isFilterAllEnabled": false,
    "filterIpList": {},
    "filterSidList": {},
    "filterUserList": {},
    "isRobotEnabled": false,
    "robot": {
        "initialCount": 10,
        "incrementCount": 1
    },
    "expired": false,
    "maxConcurrentUser": -1,
    "maxPushingTime": -1
}
```



