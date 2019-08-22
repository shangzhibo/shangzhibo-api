# 活动 API

## 接口

创建活动

```javascript
POST /api/activity
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x8BF4;&#x660E;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x6D3B;&#x52A8;&#x540D;&#x79F0;</td>
      <td style="text-align:left">&#x662F;</td>
    </tr>
    <tr>
      <td style="text-align:left">startedAt</td>
      <td style="text-align:left">datetime</td>
      <td style="text-align:left">&#x76F4;&#x64AD;&#x5F00;&#x59CB;&#x65F6;&#x95F4;&#xFF0C;&#x683C;&#x5F0F;&#x4E3A;
        UTC &#x65F6;&#x95F4;</td>
      <td style="text-align:left">&#x5426;</td>
    </tr>
    <tr>
      <td style="text-align:left">endedAt</td>
      <td style="text-align:left">datetime</td>
      <td style="text-align:left">&#x76F4;&#x64AD;&#x7ED3;&#x675F;&#x65F6;&#x95F4;&#xFF0C;&#x683C;&#x5F0F;&#x4E3A;
        UTC &#x65F6;&#x95F4;</td>
      <td style="text-align:left">&#x5426;</td>
    </tr>
    <tr>
      <td style="text-align:left">subagentIds</td>
      <td style="text-align:left">Array&lt;Integer&gt;</td>
      <td style="text-align:left">&#x5B50;&#x8D26;&#x53F7; Id &#x96C6;&#x5408;</td>
      <td style="text-align:left">&#x5426;</td>
    </tr>
    <tr>
      <td style="text-align:left">boost</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p></p>
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
      </td>
      <td style="text-align:left">&#x5426;</td>
    </tr>
    <tr>
      <td style="text-align:left">groupId</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x6D3B;&#x52A8;&#x5206;&#x7EC4; Id</td>
      <td style="text-align:left">&#x5426;</td>
    </tr>
  </tbody>
</table>### 请求样例

```javascript
{
  "name": "创想人工智能峰会-深圳站",
  "startedAt": "2019-07-22T07:18:56.640Z",
  "endedAt": "2019-08-22T07:18:56.640Z",
  "subagentIds": [1,2]
}
```

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
| isBackupRecordEnabled | boolean | 是否启用备用录播视频 |
| isLiveEnabled | boolean | 是否开启播放页直播 |
| isFakeEnabled | boolean | 是否启用人数放大 |
| fake.baseCount | integer | 观看人数放大——基础人数 |
| fake.increaseMin | integer | 观看人数放大——每增加一次真实用户访问，观看人数增加的最小值 |
| fake.increaseMax | integer | 观看人数放大——每增加一次真实用户访问，观看人数增加的最大值 |
| isFilterAllEnabled | boolean | 是否禁言所有观众 |
| filterIpList | object | 禁言 IP 列表 |
| filterSidList | object | 禁言 Session ID 列表 |
| filterUserList | object | 禁言用户列表 |
| isRobotEnabled | boolean | 是否启用机器人 |
| robot.initialCount | integer | 机器人——初始评论数 |
| robot.incrementCount | integer | 机器人——每增长 100 个用户 PV 增加的评论数 |
| expired | boolean | 活动是否超过最大推流时长 |
| maxConcurrentUser | integer | 最大并发在线人数，-1 表示不限制最大在线人数 |
| maxPushingTime | integer | 最大推流时长，单位 秒，-1 表示不限制最大推流时长 |
| isTranscodable | boolean | 该活动能否开启活动转码功能 |
| subagentIds | Array&lt;Integer&gt; | 子账号 Id 集合 |

### 响应样例

```javascript
{
    "id": "8930091",
    "name": "哈哈哈",
    "imgCover":"//shangzhibo-img.b0.upaiyun.com/system/activity/template/default-preview.jpg",
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
    "app": "onelive",
    "stream": "893009-jksdupure",
    "progress":"OnGoing",
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
    "isTranscodable":false,
    "robot": {
        "initialCount": 10,
        "incrementCount": 1
    },
    "expired": false,
    "maxConcurrentUser": -1,
    "maxPushingTime": -1,
    "subagentIds": [1, 2]
}
```

## 响应400

#### `startedAt`、`endedAt` 值不是合法的时间格式

```javascript
{
    "status": 400,
    "name": "BadRequest",
    "message": "Invalid Date",
}
```

#### 活动名称已经存在

```javascript
{
    "status": 400,
    "name": "NameExist",
    "message": "名字已经存在",
}
```



#### 未开通直播加速功能，当且仅当参数中传递了 `boost`

```javascript
{
    "status": 400,
    "name": "BadRequest",
    "message": "您的账号未开通直播加速功能",
}
```

## 响应401

#### 没有创建子账号的权限, 当且仅当在传递参数时加入了 subagentIds 参数

```javascript
{
    "status": 401,
    "name": "Unauthorized",
    "message": "您没有创建子账号的权限",
}
```

## 响应404

#### subagentIds 中的子账号 Id 不存在时

```javascript
{
    "status": 404,
    "name": "NotFount",
    "message": "Subagent Not Found",
}
```



