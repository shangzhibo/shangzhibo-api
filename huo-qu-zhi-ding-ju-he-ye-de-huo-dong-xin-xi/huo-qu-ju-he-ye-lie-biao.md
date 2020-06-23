# 获取聚合页列表

## 接口

请求地址

```javascript
GET /api/aggregation
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| page | integer | 否 | 页码 |
| pageSize | integer | 否 | 每页几条 |

## 请求样例

```text
/api/aggregation?page=1&pageSize=10
```

## 响应参数

| 参数 | 类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| page | string | 页码 | 2 |
| pageSize | string | 一页显示几条 | 10 |
| total | string | 总条数 | 100 |
| id | string | 聚合页 ID | 3960518 |
| title | string | 主标题 | 花瓣Live |
| subtitle | string | 副标题 | 花瓣，做生活的设计师 |
| logoImg | string | logo 图片链接 | - |
| followImg | string | 关注二维码图片链接 | - |
| notification | string | 通知内容 | 9月1日推出《商业插画干货分享》课程 |
| isNotificationEnabled | boolean | 通知开关状态：true 表示开，false 表示关 | true |
| activityIds | Array of string | 聚合页内添加的活动 ID | - |

## 响应示例

```javascript
{
  "pager": {
    "page": 2,
    "pageSize": 10,
    "total": 100
  },
  "items": [
    {
      "id": "3960518",
      "title": "花瓣Live",
      "subtitle": "花瓣，做生活的设计师",
      "logoImg": "https://shangzhibo-img.b0.upaiyun.com/client/user/100290/1504090975892/1504090975903-64.png",
      "followImg": "https://shangzhibo-img.b0.upaiyun.com/client/user/100290/1504090142053/1504090142132-780.png",
      "notification": "9月1日推出《商业插画干货分享》课程",
      "isNotificationEnabled": true,
      "activityIds": [
        "stringValue"
      ],
      "activities": [
        {
          "id": "3831400",
          "name": "商业插画干货分享",
          "startedAt": "2017-09-01T12:00:00.000Z",
          "endedAt": "2017-09-01T15:00:00.000Z",
          "imgCover": "https://shangzhibo-img.b0.upaiyun.com/client/user/100290/1503893080645/bg-live@2x.png",
          "pv": 53516,
        }
      ]
    }
  ]
}
```

