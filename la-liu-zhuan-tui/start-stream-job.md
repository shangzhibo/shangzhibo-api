# 开启容器

## 接口

开启容器

```text
POST /api/v3/activity/:id/stream-jobs/:jobId/start
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

无

### 请求样例

```javascript
curl -X POST -H 'authorization: bearer <accessToken>' shangzhibo.tv/api/v3/activity/8930091/stream-jobs/21524/start
```

## 响应

http 状态码 204

