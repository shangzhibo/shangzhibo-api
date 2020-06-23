# 获取指定活动观看券配置

## 接口

```http
GET /api/v3/activity/:id/watchcode/config
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
GET /api/v3/activity/8728620/watchcode/config
```

### curl 请求示例

```bash
curl 'shangzhibo.tv/api/v3/activity/8728620/watchcode/config' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36' \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-Type: application/json'
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| isWatchcodeEnabled | boolean | 观看券观看功能开关 |
| watchcodeTimeout | integer | 过期时间, 单位秒; 0 表示永久有效 |

### 响应样例

```javascript
{
  "isWatchcodeEnabled": true,
  "watchcodeTimeout": 1036800
}
```

