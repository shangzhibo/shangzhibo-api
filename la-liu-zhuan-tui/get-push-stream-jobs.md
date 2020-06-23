# 获取推流容器列表（快捷方式）

## 接口

获取推流容器列表

```javascript
GET /api/v3/activity/:id/stream-jobs/push
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

无

### 请求样例

```javascript
curl -H 'authorization: bearer <accessToken>' shangzhibo.tv/api/v3/activity/8930091/stream-jobs/push
```

## 响应

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | integer | 容器 id |
| activityId | string | 活动 id |
| type | enum&lt;pull, push&gt; | pull 表示拉流容器，push 表示推流容器 |
| status | enum&lt;active, passive&gt; | active 表示容器已经开启，passive 表示容器已经关闭 |
| createdAt | string | 创建时间 |
| updatedAt | string | 更新时间 |

## 响应样例

```javascript
[
  {
    "id": 21526,
    "activityId": "349392",
    "type": "push",
    "party": "owner",
    "address": "rtmp://push.shangzhibo.tv/onelive/test",
    "status": "passive",
    "pid": 19213,
    "provider": "luffy",
    "createdAt": "2020-06-03T08:50:51.000Z",
    "updatedAt": "2020-06-03T08:54:04.000Z"
  },
  {
    "id": 21527,
    "activityId": "349392",
    "type": "push",
    "party": "owner",
    "address": "rtmp://push.shangzhibo.tv/onelive/test",
    "status": "passive",
    "pid": null,
    "provider": "luffy",
    "createdAt": "2020-06-03T09:06:09.000Z",
    "updatedAt": "2020-06-03T09:06:09.000Z"
  },
  {
    "id": 21528,
    "activityId": "349392",
    "type": "push",
    "party": "owner",
    "address": "rtmp://push.shangzhibo.tv/onelive/test",
    "status": "passive",
    "pid": null,
    "provider": "luffy",
    "createdAt": "2020-06-03T09:06:24.000Z",
    "updatedAt": "2020-06-03T09:06:24.000Z"
  }
]
```

