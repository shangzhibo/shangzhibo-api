# 评论审核（管理员）

## 接口

评论审核

```javascript
PUT /api/activity/{id}/comment
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| contentId | integer | 评论 Id | 是 |
| status | enum | 更新评论状态，pending 待审核 passed 审核通过 failed 审核失败 | 是 |

### 请求样例

```javascript
{
  "commentId": 42,
  "status": "pending"
}
```

## 响应

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | integer | 评论 ID |
| status | enum | 评论状态，pending 待审核 passed 审核通过 failed 审核失败 |
| userId | integer | 用户 Id, 用户未登录时不返回 |
| sid | string | sessionId |

### 响应样例

```javascript
{
  "id": 42,
  "status": "pending",
  "userId": 1234567,
  "sid": "tn0JKSxGryT2-xTGbsbxZ0sSDy7iLqmY",
}
```

