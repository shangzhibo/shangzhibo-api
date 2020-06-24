## 获取指定活动信息

### 接口

获取活动信息

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
/api/activity/10075533
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| id | string | 活动 ID |
| name | string | 活动名称 |
| imgCover | string | 封面图片 |
| categoryId | integer | 活动分类 ID |
| status | string | 活动状态，enabled 允许推流 disabled 禁止推流 forbidden 管理员禁止推流 |
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
| progress | string | 活动进程参数，未开始 NotStart, 直播中 \(OnGoing\), 已结束 \(Finished\) |
| authKeys | object | 如果没有开启防盗链，不会返回该参数；开启防盗链后 default 为 RTMP 流的密钥，m3u8 为HLS 流密钥 |
| isPrologueEnabled | boolean | 是否启用预设视频 |
| isLiveEnabled | boolean | 是否开启播放页直播 |
| isFakeEnabled | boolean | 是否启用人数放大 |
| fake.baseCount | integer | 观看人数放大——基础人数 |
| fake.increaseMin | integer | 观看人数放大——每增加一次真实用户访问，观看人数增加的最小值 |
| fake.increaseMax | integer | 观看人数放大——每增加一次真实用户访问，观看人数增加的最大值 |
| isFilterAllEnabled | boolean | 是否禁言所有观众 |
| isRobotEnabled | boolean | 是否启用机器人 |
| robot.initialCount | integer | 机器人——初始评论数 |
| robot.incrementCount | integer | 机器人——每增长 100 个用户 PV 增加的评论数 |
| expired | boolean | 活动是否超过最大推流时长 |
| maxConcurrentUser | integer | 最大并发在线人数，-1 表示不限制最大在线人数 |
| maxPushingTime | integer | 最大推流时长，单位 秒，-1 表示不限制最大推流时长 |
| isTranscodable | boolean | 该活动能否开启活动转码功能 |
| pullUrls | object | 拉流地址集合 |
| pullUrls.default | string | rtmp 拉流地址 |
| pullUrls.flv | string | flv 拉流地址 |
| pullUrls.m3u8 | string | hls 拉流地址 |

#### 响应样例

```json
{
    "isArchived":false,
    "isPushing":false,
    "id":"10075533",
    "agentId":105131,
    "categoryId":1,
    "name":"热敷法发",
    "status":"enabled",
    "startedAt":"2020-06-30T06:31:00.000Z",
    "endedAt":"2020-07-23T06:31:00.000Z",
    "pushDomain":"push.shangzhibo.tv",
    "pullDomain":"play.shangzhibo.tv",
    "groupId":-1,
    "createdAt":"2020-05-29T02:01:10.000Z",
    "updatedAt":"2020-06-22T06:31:46.000Z",
    "progress":"NotStart",
    "app":"onelive",
    "stream":"10075533-sTd6IzKoEU",
    "isPrologueEnabled":true,
    "isEpilogueEnabled":true,
    "isLiveEnabled":true,
    "fake":{
        "baseCount":0,
        "increaseMin":1,
        "increaseMax":1
    },
    "isFakeEnabled":false,
    "isFilterAllEnabled":false,
    "isRobotEnabled":false,
    "robot":{
        "initialCount":10,
        "incrementCount":1,
        "commentLibraryId":null
    },
    "expired":false,
    "liveProvider":"aliyun",
    "maxConcurrentUser":-1,
    "maxPushingTime":-1,
    "maxEpilogueTime":-1,
    "isTranscodable":false,
    "imgCover":"https://doc.shangzhibo.tv/system/activity/template/default-preview.jpg",
    "pullUrls":{
        "default":"play.shangzhibo.tv/onelive/10075533-sTd6IzKoEU",
        "flv":"play.shangzhibo.tv/onelive/10075533-sTd6IzKoEU.flv",
        "m3u8":"play.shangzhibo.tv/onelive/10075533-sTd6IzKoEU.m3u8"
    }
}
```



