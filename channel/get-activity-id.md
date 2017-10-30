## 获取频道

### 接口

获取频道

```js
GET /api/activity/{id}
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```
注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

无

#### 请求样例

```js
/api/activity/8728620
```

### 响应

| 参数                    | 参数类型                                     | 参数说明                                     |
| --------------------- | ---------------------------------------- | ---------------------------------------- |
| id                    | string                                   | 活动 ID                                    |
| name                  | string                                   | 活动名称                                     |
| categoryId            | integer                                  | 活动分类 ID                                  |
| status                | enum('enabled', 'disabled', 'forbidden', 'deleted') | 活动状态，enabled 用户允许推流，disabled 用户禁止推流，forbidden 管理员禁止推流，deleted 活动删除 |
| agentId               | integer                                  | 账号 ID                                    |
| startedAt             | string                                   | 活动开始时间                                   |
| endedAt               | string                                   | 活动结束时间                                   |
| createdAt             | string                                   | 活动创建时间                                   |
| updatedAt             | string                                   | 活动配置更新时间                                 |
| pullDomain            | string                                   | 直播推流地址                                   |
| pushDomain            | string                                   | 直播拉流地址                                   |
| app                   | string                                   | 应用名                                      |
| stream                | string                                   | 流名                                       |
| isPushing             | boolean                                  | 是否在推流                                    |
| maxConcurrentUser     | integer                                  | 最大并发在线人数，-1 表示不限制最大在线人数                  |
| maxPushingTime        | integer                                  | 最大推流时长，单位 秒，-1 表示不限制最大推流时长               |
| forbiddenReason       | string                                   | 禁播原因，仅当状态为 forbidden 时才出现                |
| isPrologueEnabled     | boolean                                  | 是否启用预设视频                                 |
| isEpilogueEnabled     | boolean                                  | 是否启用回看视频                                 |
| isBackupRecordEnabeld | boolean                                  | 是否启用备用录播视频                               |
| isLiveEnabled         | boolean                                  | 是否开启观看页直播                                |
| isFilterAllEnabled    | boolean                                  | 是否禁言所有观众                                 |
| isFakeEnabled         | boolean                                  | 是否启用人数放大                                 |
| fake.baseCount        | integer                                  | 基础人数                                     |
| fake.increaseMin      | integer                                  | 每增加一次真实用户访问，观看人数增加最小值                    |
| fake.increaseMax      | integer                                  | 每增加一次真实用户访问，观看人数增加最大值                    |
| isRobotEnabled        | boolean                                  | 是否启用机器人                                  |
| robot.initialCount    | integer                                  | 初始评论数                                    |
| robot.incrementCount  | integer                                  | 每增加100个用户 PV 增加的评论数                      |
| filterIpList          | object                                   | 禁言 IP 列表                                 |
| filterSidList         | object                                   | 禁言 sessionID 列表                          |
| filterUserList        | object                                   | 禁言用户列表                                   |
| expired               | boolean                                  | 频道是否超过最大推流时长                             |

#### 响应样例

```json
{
  "id": "8728620",
  "name": "测试",
  "categoryId": 1,
  "status": "enabled",
  "agentId": 100020,
  "startedAt": "2017-10-27T11:13:40.000Z",
  "endedAt": "2017-10-27T15:13:40.000Z",
  "pushDomain": "push.shangzhibo.tv",
  "pullDomain": "play.shangzhibo.tv",
  "isPushing": false,
  "createdAt": "2017-10-27T10:13:41.000Z",
  "updatedAt": "2017-10-27T16:02:35.000Z",
  "app": "SyeRAUYgRb",
  "stream": "r1-RRItgC-?auth_key=1540635222-0-0-1b5a9f570a0192c8d98c8d5d086fb71e",
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

