# 下载观看券绑定记录

## 接口

```http
GET /activity/:id/watchcode/bindings/download
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

无

### 请求样例

```http
GET /api/activity/8728620/watchcode/bindings/download
```

### curl 请求示例

```bash
curl 'shangzhibo.tv/api/activity/8728620/watchcode/bindings/download' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36' \
  -H 'Authorization: Bearer <access_token>'
```

### 响应

观看券绑定记录文件

