# 获取指定活动历史评论信息

## 接口

获取历史评论

```javascript
GET /api/user/activity/:id/comment
```

## 授权

无需授权

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| page | integer | 页码 | 否 |
| limit | integer | 每页数量 | 否 |
| sort | string | 排序方式 | 否 |

### 请求样例

```javascript
/api/user/activity/8930091/comment?page=42&limit=10&sort=id\ DESC
```

## 响应

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| total | integer | 总数 |
| limit | integer | 每页数量 |
| page | integer | 页码 |
| data | array | 数据 |

### data

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | integer | 评论 ID |
| status | enum | 评论状态，取值：`pending` 待审核、 `passed`已通过、`failed`禁用 |
| content | string | 评论内容 |
| createdAt | string | 创建时间 |
| updatedAt | string | 更新时间 |
| activityId | string | 活动 ID |
| user | object | 用户信息 |

### 用户信息

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| role | enum | 角色，取值：`agent` 管理员、 `user`登录用户、`anonymous`匿名用户 |
| nickname | string | 用户名 |
| avatar | string | 用户头像 |

### 响应样例

```javascript
{
  "total": 42,
  "page": 42,
  "limit": 42,
  "data": [
    {
      "id": 42,
      "user": {
        "role": "agent",
        "nickname": "stringValue",
        "avatar": "stringValue"
      },
      "activityId": "stringValue",
      "status": "pending",
      "content": "stringValue",
      "createdAt": "stringValue",
      "updatedAt": "stringValue"
    }
  ]
}
```

