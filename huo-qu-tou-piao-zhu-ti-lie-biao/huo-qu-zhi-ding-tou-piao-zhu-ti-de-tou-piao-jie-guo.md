# 获取指定投票主题的投票结果

## 接口

获取投票结果（限制每秒最多调用 3 次）

```javascript
GET /api/activity/vote/{votedId}/result?format=json
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）。

## 参数

无

### 请求样例

```javascript
/api/activity/vote/587/result?format=json
```

## 响应

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| nickname | string | 用户昵称 |
| avatar | string | 用户头像 |
| uid | integer | 唯一标识用户的 ID，数字类型 |
| strUid | string | 唯一标识用户的 ID，字符串类型 |
| voteChoice | string | 该用户选择的投票项 |
| createdAt | string | 投票对劲 |

### 响应样例

```javascript
[
    {
        "userId": 5026588,
        "user": {
            "id": 5026588,
            "avatar": "http://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTKdTOKORMFGGUgib8thbKENnzZtpy0iabWcdVkh9eiaK9Ros4tcJtE88baaR7MxBbKvqTzhkk2vBoYiag/132",
            "nickname": "sdas",
            "uid": null,
            "strUid": null
        },
        "voteChoice": "对",
        "createdAt": "2019-04-22 14:15:45"
    },
    {
        "userId": 6692312,
        "user": {
            "id": 6692312,
            "avatar": "http://thirdwx.qlogo.cn/mmopen/vi_32/vcAib31vh8HWIldiayAmL88DDtAJsIZFp19zlPCCu8IjPdcAUq5biam36QVc07OjOhbQHhhMt1sboe0bEyUvFJh3Q/132",
            "nickname": "Summer",
            "uid": null,
            "strUid": null
        },
        "voteChoice": "对",
        "createdAt": "2019-04-22 14:24:20"
    }
]
```

