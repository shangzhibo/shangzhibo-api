# 生成单个观看券

## 接口

```http
POST /api/activity/:id/watchcode
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

```http
POST /api/activity/8728620/watchcode
```

### curl 请求示例

```bash
curl 'shangzhibo.tv/api/activity/8728620/watchcode' \
  -X 'POST' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36' \
  -H 'Content-Type: application/json'
  -H 'Authorization: Bearer <access_token>'
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| code | string | 观看券 id |

### 响应样例

```javascript
{
    "code":"5BxdEHoh6"
}
```

