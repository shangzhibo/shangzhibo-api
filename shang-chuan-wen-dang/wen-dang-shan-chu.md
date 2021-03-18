# 文档删除

## 接口

删除文档

```javascript
DELETE /api/v2/activity/:id/doc/:docId
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: multipart/form-data
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

无

### 请求样例

```bash
curl -H "Authorization: bearer <access token>"
-X "DELETE" http://shangzhibo.tv/api/v2/activity/:id/doc/:docId
```

## 响应

### 响应样例200

```javascript
{
    result: true
}
```

### 响应样例 404

```javascript
{
    "name":"NotFound",
    "message":"Doc Not Found",
    "status":404
}
```

### 响应样例 429

频率限制为 10次 / 秒

```javascript
{
    "name":"TooManyRequests",
    "message":"请求速度太频繁了, 请于xxx后重试",
    "status":429
}
```

