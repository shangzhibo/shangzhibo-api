# 绑定或解绑指定的观看券

## 接口

```http
PUT /api/activity/:id/watchcode
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数   | 参数类型     | 参数说明                              | 是否必填 |
| ------ | ------------ | ------------------------------------- | -------- |
| code   | string       | 授权观看的方式                        | 是       |
| type   | enum<string> | bind 绑定; unbind 解绑; 默认为 unbind | 否       |
| userId | integer      | 观看券对应的用户                      | 是       |

### 请求样例

```http
PUT /api/activity/8728620/watchcode

{
	"code":"sz_FOz6YT",
	"userId":2184958,
	"type":"unbind"
}
```

### curl 请求示例

```bash
curl 'shangzhibo.tv/api/activity/8728620/watchcode' \
  -X 'PUT' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36' \
  -H 'Authorization: Bearer <access_token>'
  -H 'Content-Type: application/json' \
  --data-binary '{"code":"sz_FOz6YT","userId":2184958,"type":"unbind"}'
```

### 响应样例

```javascript
{
  "result":true
}
```
