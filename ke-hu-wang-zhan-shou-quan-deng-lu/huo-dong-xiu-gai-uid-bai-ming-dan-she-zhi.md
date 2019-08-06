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

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">allowedPartnerUidList</td>
      <td style="text-align:left">Array&lt;Integer|String&gt;</td>
      <td style="text-align:left">
        <p>&#x8BBE;&#x7F6E;&#x5F53;&#x524D;&#x6D3B;&#x52A8;&#x7684; uid &#x767D;&#x540D;&#x5355;&#x5217;&#x8868;</p>
        <p>&#xFF08;&#x53EF;&#x4EE5;&#x8BBE;&#x7F6E; uid &#x6570;&#x5B57;&#x578B;&#x6216;
          strUid &#x5B57;&#x7B26;&#x4E32;&#x578B;&#xFF09;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">isWhiteListEnabled</td>
      <td style="text-align:left">Boolean</td>
      <td style="text-align:left">true &#x8868;&#x793A;&#x529F;&#x80FD;&#x5F00;&#x542F;&#xFF0C;false &#x8868;&#x793A;&#x529F;&#x80FD;&#x5173;&#x95ED;</td>
    </tr>
  </tbody>
</table>## 响应

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
