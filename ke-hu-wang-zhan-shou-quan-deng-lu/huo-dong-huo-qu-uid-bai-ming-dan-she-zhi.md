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

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 响应

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |


<table>
  <thead>
    <tr>
      <th style="text-align:left">allowedPartnerUidList</th>
      <th style="text-align:left">Array&lt;String&gt;</th>
      <th style="text-align:left">
        <p>&#x5F53;&#x524D;&#x6D3B;&#x52A8;&#x7684; uid &#x767D;&#x540D;&#x5355;&#x5217;&#x8868;</p>
        <p>&#xFF08;&#x4E3A;&#x4E86;&#x4FDD;&#x6301;&#x683C;&#x5F0F;&#x7EDF;&#x4E00;&#xFF0C;&#x6211;&#x4EEC;&#x5728;&#x8FD4;&#x56DE;&#x503C;&#x4E2D;&#x5C06;
          uid &#x6570;&#x5B57;&#x578B;&#x548C; strUid &#x5B57;&#x7B26;&#x4E32;&#x578B;&#x90FD;&#x8F6C;&#x6362;&#x4E3A;&#x5B57;&#x7B26;&#x4E32;&#x7C7B;&#x578B;&#xFF09;</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>```javascript
{
  "allowedPartnerUidList": ["1234","32434"],
  "isWhiteListEnabled": false,
}
```

