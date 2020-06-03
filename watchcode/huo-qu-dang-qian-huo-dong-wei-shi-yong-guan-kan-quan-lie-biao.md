# 获取当前活动未使用观看券列表

## 接口

```http
GET /api/activity/:id/watchcode
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| page | integer | 页码, 默认为 1 | 否 |
| pageSize | integer | 每页条数, 默认为 10 | 否 |

### 请求样例

```http
GET /api/activity/8728620/watchcode?page=1&pageSize=10
```

### curl 请求示例

```bash
curl 'shangzhibo.tv/api/activity/8728620/watchcode?page=1&pageSize=10' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36' \
  -H 'Authorization: Bearer <access_token>'
```

### 响应

| 参数 | 类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| page | integer | 页码 | 2 |
| pageSize | integer | 每页条数 | 10 |
| total | integer | 总条数 | 100 |
| isUsed | boolean | 该观看券是否被使用 | false |
| code | string | 观看券 code | 45Y19rwHy |
| createdAt | string | 观看券生成时间 | 2020-05-22T15:24:27.000Z |

### 响应样例

```javascript
{
    "pager":{
        "page":1,
        "pageSize":10,
        "total":3
    },
    "items":[{
            "isUsed":false,
            "code":"45Y19rwHy",
            "createdAt":"2020-05-18T02:13:27.000Z"
        }, {
            "isUsed":false,
            "code":"U_aFnZoDy",
            "createdAt":"2020-05-22T01:43:46.000Z"
        }, {
            "isUsed":false,
            "code":"39cwR2TWX",
            "createdAt":"2020-05-22T01:48:43.000Z"
        }]
}
```

