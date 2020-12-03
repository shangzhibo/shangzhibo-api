# 活动删除

## 接口

请求地址

```javascript
DELETE /api/activity/:id
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 请求样例

```typescript
DETELE /api/activity/:id
```

## 响应示例200

```javascript
{
   "result": true
}
```

## 响应示例 400

当活动下有礼物或者观看页付费收益，则该活动无法删除

```javascript
{
    "status": "400",
    "message": "该活动下有收益，无法删除",
    "name": "BadRequest",
}
```

