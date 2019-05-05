## 获取指投票主题列表

### 接口

获取投票主题列表

```js
GET /api/activity/{id}/vote
```

### 授权

请求 header

```http
Authorization: Bearer <accessToken>
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| --- | --- | --- | --- |
| page | integer | 页码 | 否 |
| limit | integer | 每页数量 | 否 |

#### 请求样例

```js
/api/activity/5966003/vote
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| id | string | 投票主题 id |
| activityId | string | 活动 id |
| title | string | 投票主题名称 |
| endedAt | string | 投票主题结束时间 |
| maxAllowedChoice | string | 每个用户最多允许投票数 |
| isImageContained | boolean | 是否允许为投票项附加图片 |
| isDailyEnabled | boolean | 是否允许每日投票 |
| createdAt | string | 创建时间 |
| updatedAt | string | 更新时间 |
| choices | array | 投票选项 |
| - id | string | 投票项 id |
| - votedId | string | 投票主题 id |
| - text | string | 投票选项 |
| - imageUrl | string | 投票选项附加图片 |
| - voteCount | string | 得票数 |
| - createdAt | string | 创建时间 |
| - updatedAt | string | 更新时间 |

#### 响应样例

```js
{
    "pager": {
        "page": 1,
        "pageSize": 10,
        "total": 2
    },
    "items": [
        {
            "id": 622,
            "activityId": "5966003",
            "title": "直播竞答：你认为上直播牛吗？",
            "endedAt": "2019-04-30T08:04:55.000Z",
            "maxAllowedChoice": 1,
            "isImageContained": false,
            "isDailyEnabled": false,
            "isEnabled": false,
            "createdAt": "2019-05-05T03:34:24.000Z",
            "updatedAt": "2019-05-05T03:34:24.000Z",
            "choices": [
                {
                    "id": 3339,
                    "voteId": 622,
                    "text": "对",
                    "imageUrl": "//doc.shangzhibo.tv/tmp/%E6%9A%82%E6%97%A0.svg",
                    "index": 0,
                    "voteCount": 0,
                    "createdAt": "2019-05-05T03:34:27.000Z",
                    "updatedAt": "2019-05-05T03:34:27.000Z"
                },
                {
                    "id": 3340,
                    "voteId": 622,
                    "text": "错",
                    "imageUrl": "//doc.shangzhibo.tv/tmp/%E6%9A%82%E6%97%A0.svg",
                    "index": 0,
                    "voteCount": 0,
                    "createdAt": "2019-05-05T03:34:30.000Z",
                    "updatedAt": "2019-05-05T03:34:30.000Z"
                }
            ],
            "totalCount": 0
        },
        {
            "id": 587,
            "activityId": "5966003",
            "title": "直播竞答：你认为上直播牛吗？",
            "endedAt": "2019-04-30T08:04:55.000Z",
            "maxAllowedChoice": 1,
            "isImageContained": false,
            "isDailyEnabled": false,
            "isEnabled": false,
            "createdAt": "2019-04-22T06:13:20.000Z",
            "updatedAt": "2019-04-23T06:55:10.000Z",
            "choices": [
                {
                    "id": 3241,
                    "voteId": 587,
                    "text": "对",
                    "imageUrl": "//doc.shangzhibo.tv/tmp/%E6%9A%82%E6%97%A0.svg",
                    "index": 0,
                    "voteCount": 2,
                    "createdAt": "2019-04-22T06:13:25.000Z",
                    "updatedAt": "2019-05-05T02:34:16.000Z"
                },
                {
                    "id": 3242,
                    "voteId": 587,
                    "text": "错",
                    "imageUrl": "//doc.shangzhibo.tv/tmp/%E6%9A%82%E6%97%A0.svg",
                    "index": 0,
                    "voteCount": 0,
                    "createdAt": "2019-04-22T06:13:29.000Z",
                    "updatedAt": "2019-05-05T02:34:16.000Z"
                }
            ],
            "totalCount": 2
        }
    ]
}
```



