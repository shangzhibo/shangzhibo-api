# 批量生成并下载观看券

## 接口

```http
GET /activity/:id/watchcode/download
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| number | integer | 批量生成的观看券数量，每次最多生成 100 个 | 是 |

### 请求样例

```http
GET /api/activity/8728620/watchcode/download
```

### curl 请求示例

```bash
curl 'shangzhibo.tv/api/activity/8728620/watchcode/download' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36' \
  -H 'Authorization: Bearer <access_token>'
```

### 响应

观看券列表文件

