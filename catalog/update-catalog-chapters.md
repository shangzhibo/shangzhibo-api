# 更新合辑内容设置

## 接口

创建合辑

```javascript
PUT /api/v3/catalog/:catalogId/chapters
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| catalogId | integer | 是 | 合辑 ID |
| chapters | array<object> | 是 | 合辑内容 |
| chapters[N].selection | string | 章节名称, 默认为空字符串 |
| chapters[N].activityIds | array<string> | 活动 ID 列表 |

### 请求示例

```bash 
curl -H "Content-Type: application/json" \
  -H "Authorization: Bearer <accessToken>"  \
  -X "PUT" http://shangzhibo.tv/api/v3/catalog/1/chapters -d $'{
    "chapters": [
        {
            "selection": "第一章",
            "activityIds": [
                "10000002"
            ]
        }
    ]
}'
```

## 响应 200

| 参数 | 参数类型 | 描述 |
| :--- | :--- | :--- |
| chapters | array<object> | 合辑内容 |
| chapters[N].selection | string | 章节名称, 默认为空字符串 |
| chapters[N].activityIds | array<string> | 活动 ID 列表 |
| chapters[N].activities | array<object> | 活动列表对应的活动内容 |
| chapters[N].activities[M].id | string | 活动ID |
| chapters[N].activities[M].name | string | 活动名称 |
| chapters[N].activities[M].link | string | 活动打开链接 |
| chapters[N].activities[M].type | enum["video", "live"] | 活动类型， video 表示视频，live 表示直播 |


### 响应样例

```javascript
{
  "chapters": [
    {
      "selection": "第一章",
      "activityIds": [
        "10000002"
      ],
      "activities": [
        {
          "id": "10000002",
          "name": "测试活动",
          "type": "video",
          "link": "http://localhost:2127/watch/10000002"
        }
      ]
    }
  ]
}
```

## 响应 400

### 活动已被其他合辑使用

```javascript
{
  "message": "Activity 10000002 has been used in another catalog",
  "status": 400,
  "name": "BadRequest"
}
```

## 响应 404

### 活动不存在

```javascript
{
  "message": "Activity 10000002 Not Found",
  "status": 404,
  "name": "NotFound"
}
```
