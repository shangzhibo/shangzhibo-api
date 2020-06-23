# 获取观看券绑定记录

## 接口

```http
GET /api/activity/:id/watchcode/bindings
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
| page | integer | 页码, 默认为 1 | 否 |
| pageSize | integer | 每页条数, 默认为 10 | 否 |

### 请求样例

```http
GET /api/activity/8728620/watchcode/bindings?page=1&pageSize=10
```

### curl 请求示例

```bash
curl 'shangzhibo.tv/api/activity/8728620/watchcode/bindings?page=1&pageSize=10' \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36' \
  -H 'Authorization: Bearer <access_token>'
```

### 响应

| 参数 | 类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| page | integer | 页码 | 2 |
| pageSize | integer | 每页条数 | 10 |
| total | integer | 总条数 | 100 |
| isUsed | boolean | 该观看券是否被使用 | true |
| code | string | 观看券 code | 45Y19rwHy |
| createdAt | string | 观看券生成时间 | 2020-05-22T15:24:27.000Z |
| userId | integer | 被绑定用户 id | 212545 |
| bindedAt | string | 绑定时间 | 2020-05-22T15:24:27.000Z |
| expiredAt | string | 观看券过期时间 | 2020-05-22T15:24:27.000Z |
| nickname | string | 用户昵称 | hello |
| avatar | string | 用户头像 | [http://thirdwx.qlogo.cn/mmopen/vi\_32/Q0j4TwGTfTJdhX8EJDyyxX3NHRRqu30ia6ibCdft438GpiayNiaO2NYoKxiaCQCQIx0GMu3CKvN0jHu1lzNWufaS9ibA/132](http://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTJdhX8EJDyyxX3NHRRqu30ia6ibCdft438GpiayNiaO2NYoKxiaCQCQIx0GMu3CKvN0jHu1lzNWufaS9ibA/132) |

### 响应样例

```javascript
{
    "pager":{
        "page":1,
        "pageSize":10,
        "total":1
    },
    "items":[{
            "code":"sz_FOz6YT",
            "isUsed":true,
            "createdAt":"2020-05-22T07:01:41.000Z",
            "userId":2184958,
            "bindedAt":"2020-05-22T07:01:47.000Z",
            "expiredAt":"2020-06-03T07:01:47.818Z",
            "user":{
                "nickname":"hello",
                "avatar":"http://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTJdhX8EJDyyxX3NHRRqu30ia6ibCdft438GpiayNiaO2NYoKxiaCQCQIx0GMu3CKvN0jHu1lzNWufaS9ibA/132"
            }
        }]
}
```

