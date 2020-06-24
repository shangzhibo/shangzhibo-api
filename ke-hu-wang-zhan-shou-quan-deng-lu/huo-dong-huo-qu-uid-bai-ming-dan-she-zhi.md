---
description: 此功能仅限于开启了第三方登录定制以及 UID 白名单定制的客户使用
---

# 获取指定活动的 UID白名单

## 接口

获取 UID 白名单设置

```javascript
GET /api/activity/{id}/par-uid-whitelist
```

### 注意:

为了保持类型兼容，在返回值中会将所有的 uid 转换为 string 类型

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）。

注意：该功能需要第三方登录定制且开通 UID 白名单功能后才可以使用，具体请联系所属商务经理。

## 响应

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
|allowedPartnerUidList | Array&lt;string&gt; | 当前活动的 uid 白名单列表（为了保持格式统一，我们在返回值中将 uid 数字型和 strUid 字符串型都转换为字符串类型）|

```javascript
{
  "allowedPartnerUidList": ["1234","32434"],
  "isWhiteListEnabled": false,
}
```