## 给指定活动发送评论（观众）

### 接口

发送评论

```js
POST /api/user/activity/{id}/comment
```

### 授权

无需授权

### 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| --- | --- | --- | --- |
| content | string | 评论内容 | 是 |

#### 请求样例

```js
{
  "content": "stringValue",
}
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| id | integer | 评论 ID |
| status | enum | 评论状态，取值：`pending` 待审核、 `passed`已通过、`failed`禁用 |
| content | string | 评论内容 |
| createdAt | string | 创建时间 |
| updatedAt | string | 更新时间 |
| activityId | string | 活动 ID |
| user | object | 用户信息 |

#### 用户信息

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| role | enum | 角色，取值：`agent` 管理员、 `user`登录用户、`anonymous`匿名用户 |
| nickname | string | 用户名 |
| avatar | string | 用户头像 |

#### 响应样例

```js
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
```



