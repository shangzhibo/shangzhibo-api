# 获取指定时间段内活动历史并发人数

## 接口

获取指定时间段内活动历史并发人数, 该接口限频 1 次 / 5 秒

```javascript
GET /api/v3/activity/:id/stats/timeline
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| startedAt | string | 开始时间 | 是 |
| endedAt | string | 结束时间 | 是 |

开始时间与结束时间间隔不能超过 7 天

开始时间与结束时间格式必须符合正则: `^\d{4}-\d{2}-\d{2}T\d{2}:\d{2}:\d{2}(\.\d{0,3})?Z$`

## 请求样例

```bash
curl -H 'authorization: bearer <accessToken>' \
    https://shangzhibo.tv/api/v3/activity/:id/stats/timeline\?startedAt=2020-07-13T10:27:00Z\&endedAt=2020-07-20T10:27:00Z
```

## 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| count | integer | 并发人数 |
| time | string | 并发时间 |

## 响应示例

```javascript
[
  {
    "count": 1,
    "time": "2020-07-14T02:17:00.000Z"
  },
  {
    "count": 1,
    "time": "2020-07-14T10:08:00.000Z"
  },
  {
    "count": 10,
    "time": "2020-07-20T09:25:00.000Z"
  },
  {
    "count": 120,
    "time": "2020-07-20T09:26:00.000Z"
  }
]
```

