# 获取指定聚合页的活动信息

## 接口

获取聚合页活动信息

```javascript
GET /api/aggregation/{id}
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

无

## 请求样例

```text
/api/aggregation/6407048
```

## 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| id | string | 聚合页 ID |
| title | string | 聚合页标题 |
| subtitle | string | 聚合页副标题 |
| logoImg | string | 聚合页 LOGO 图片地址 |
| followImg | string | 聚合页关注二维码图片地址 |
| notification | string | 通知内容 |
| isNotificationEnabled | boolean | 通知开关 |

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
      "id": "6407048",
      "agentId": 42,
      "title": "聚合页标题",
      "subtitle": "聚合页测试标题",
      "logoImg": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/followImg.jpg",
      "followImg": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/followImg.jpg",
      "notification": "通知内容通知内容通知内容通知内容",
      "isNotificationEnabled": true,
      "activityIds": [
        "stringValue"
      ],
      "activities": [
        {
          "id": "4296237",
          "name": "活动名称",
          "startedAt": "2018-06-08 18:18:18",
          "endedAt": "2018-08-08 18:18:18",
          "imgCover": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/followImg.jpg",
          "pv": 10942,//活动页显示的在线人数
          "isEpilogueEnabled": true
        }
      ]
    }
  ]
}
```

