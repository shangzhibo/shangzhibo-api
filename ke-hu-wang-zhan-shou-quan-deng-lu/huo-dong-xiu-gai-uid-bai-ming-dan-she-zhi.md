---
description: 此功能仅限于开启了第三方登录定制以及 UID 白名单定制的客户使用
---

# 修改指定活动的 UID白名单

## 接口

修改 UID 白名单设置

```javascript
PUT /api/activity/{id}/par-uid-whitelist
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）。

注意：该功能需要第三方登录定制且开通 UID 白名单功能后才可以使用，具体请联系所属商务经理。

## 参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
|allowedPartnerUidList | Array&lt;string|integer&gt; | 当前活动的 uid 白名单列表 |

### 响应样例 200

```javascript
{
  "result": true
}
```

### 响应样例 400

```javascript
{
    "name":"BadRequest",
    "message":"您未开启第三方定制功能, 请先开通后再进行操作",
    "status":400
}
```

```javascript
{
    "name":"BadRequest",
    "message":"您未开启 uid 白名单功能, 请先开通后再进行操作",
    "status":400
}
```