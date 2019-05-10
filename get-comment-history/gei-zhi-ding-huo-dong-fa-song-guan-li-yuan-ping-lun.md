# 给指定活动发送评论（管理员）

## 接口

发送评论

```javascript
POST /api/activity/{id}/comment
```

## 授权

请求 header

```text
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| content | string | 评论内容 | 是 |

### 请求样例

```javascript
{
  "content": "stringValue",
}
```

## 响应

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
  "id": 4535683,
  "user": {
    "role": "agent",
    "nickname": "管理员",
    "avatar": "stringValue"
  },
  "activityId": "7397573",
  "status": "passed",
  "content": "活动已经完美结束了，可以在活动结束后加群：QQ123123123",
  "createdAt": "2018-07-04 16:47:55",
  "updatedAt": "2018-07-04 16:47:55"
}
```

