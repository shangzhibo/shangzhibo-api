# 创建活动

## 接口

创建活动

```typescript
POST /api/activity
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| name | string | 活动名称 | 是 |
| startedAt | datetime | 直播开始时间，格式为 UTC 时间 | 否 |
| endedAt | datetime | 直播结束时间，格式为 UTC 时间 | 否 |
| subagentIds | Array&lt;Integer&gt; | 子账号 Id 集合 | 否 |
| transcodeEnabled | Boolean | 是否开启画质控制\(需要开启直播转码功能\) | 否 |

<table>
  <thead>
    <tr>
      <th style="text-align:left">boost</th>
      <th style="text-align:left">string</th>
      <th style="text-align:left">
        <ul>
          <li>push-global &#x5168;&#x7403;&#x63A8;&#x6D41;</li>
          <li>push-us &#x7F8E;&#x56FD;&#x63A8;&#x6D41;</li>
          <li>push-de &#x5FB7;&#x56FD;&#x63A8;&#x6D41;</li>
          <li>push-hk &#x9999;&#x6E2F;&#x63A8;&#x6D41;</li>
          <li>push-sg &#x65B0;&#x52A0;&#x5761;&#x63A8;&#x6D41;</li>
          <li>pull-global &#x5168;&#x7403;&#x64AD;&#x653E;</li>
          <li>pull-us &#x7F8E;&#x56FD;&#x64AD;&#x653E;</li>
          <li>pull-de &#x5FB7;&#x56FD;&#x64AD;&#x653E;</li>
          <li>pull-hk &#x9999;&#x6E2F;&#x64AD;&#x653E;</li>
          <li>pull-sg &#x65B0;&#x52A0;&#x5761;&#x64AD;&#x653E;</li>
        </ul>
        <p>&#x8BE5;&#x53C2;&#x6570;&#x9700;&#x989D;&#x5916;&#x5F00;&#x901A;&#x6D77;&#x5916;&#x8282;&#x70B9;&#x529F;&#x80FD;</p>
      </th>
      <th style="text-align:left">&#x5426;</th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

````text
## 响应200

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | string | 活动 ID |
| name | string | 活动名称 |
| imgCover | string | 封面图片 |
| categoryId | integer | 活动分类 ID |
| status | string | 活动状态，enabled 允许推流 disabled 禁止推流 forbidden 管理员禁止推流 deleted 活动已被删除 |
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
| subagentIds | Array&lt;Integer&gt; | 子账号 Id 集合 |
| pullUrls | object | 拉流地址集合 |
| pullUrls.default | string | rtmp 拉流地址 |
| pullUrls.flv | string | flv 拉流地址 |
| pullUrls.m3u8 | string | hls 拉流地址 |


### 响应样例

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
````

## 响应 400

### `startedAt`、`endedAt` 值不是合法的时间格式

```javascript
{
    "status": 400,
    "name": "BadRequest",
    "message": "Invalid Date",
}
```

### 活动名称已经存在

```javascript
{
    "status": 400,
    "name": "NameExist",
    "message": "名字已经存在",
}
```

### 未开通直播加速功能，当且仅当参数中传递了 `boost`

```javascript
{
    "status": 400,
    "name": "BadRequest",
    "message": "您的账号未开通直播加速功能",
}
```

## 响应 401

### 没有创建子账号的权限, 当且仅当在传递参数时加入了 subagentIds 参数

```javascript
{
    "status": 401,
    "name": "Unauthorized",
    "message": "您没有创建子账号的权限",
}
```

## 响应 404

### subagentIds 中的子账号 Id 不存在时

```javascript
{
    "status": 404,
    "name": "NotFount",
    "message": "Subagent Not Found",
}
```
