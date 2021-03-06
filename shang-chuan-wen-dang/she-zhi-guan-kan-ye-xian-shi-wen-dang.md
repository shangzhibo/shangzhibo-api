---
description: 设置观看页显示文档
---

# 设置观看页显示文档

## 接口

使用修改模板接口

```javascript
PUT /api/v2/activity/:id/doc/default
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| currentDocId | integer | 需要在观看页显示的文档 Id | 是 |

### 请求样例

```javascript
{
  "currentDocId": 10,
}
```

## 响应

### 响应样例200

```javascript
{
    "result": true
}
```

### 响应样例 429

接口限频 10次/ 秒

```javascript
{
    "name":"TooManyRequests",
    "message":"请求速度太频繁了, 请于xxx后重试",
    "status":429
}
```

