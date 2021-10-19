---
description: 账号下所有用户的评论信息
---

# 获取指定账号下评论信息

## 接口

```
GET api/agent/:id/comment
```

## 授权

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注： 请将上方的替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数        | 参数类型    | 参数说明                                     | 是否必填 | 示例                       |
| --------- | ------- | ---------------------------------------- | ---- | ------------------------ |
| startedAt | string  | 查询范围时间起点                                 | 是    | 2021-10-18T10:23:24.000Z |
| endedAt   | string  | 查询范围时间终点，最大时间范围 1 天                      | 是    | 2021-10-19T10:23:24.000Z |
| page      | integer | 页码                                       | 否    | 1                        |
| pageSize  | integer | 每页数量                                     | 否    | 10                       |
| order     | string  | 排序方式，枚举值\['id desc', 'id asc']           | 否    | id desc                  |
| status    | string  | 评论状态，枚举值\['pending', 'passed', 'failed'] | 否    | passed                   |

## 请求样例

```
/api/agent/xxxx/comment?startedAt=2021-10-18T10:23:24.000Z&endedAt=2021-10-19T10:23:24.000Z&status=passed&order=id desc&page=1&pageSize=20
```

## 响应参数

| 参数    | 参数类型   |
| ----- | ------ |
| pager | object |
| items | object |

#### **pager**参数

| 参数       | 参数类型    | 参数说明    | 示例 |
| -------- | ------- | ------- | -- |
| page     | integer | 页码      | 1  |
| pageSize | integer | 每页最多数量  | 20 |
| total    | integer | 查询的结果总数 | 10 |

#### **items**参数

| 参数          | 参数类型    | 参数说明                | 示例                                  |
| ----------- | ------- | ------------------- | ----------------------------------- |
| userId      | integer | 用户Id                | 123456789                           |
| avatar      | string  | 用户头像                | https://jldfsjfkldjsklfjdlsk-B6OFs4 |
| nickname    | string  | 用户昵称                | 没用的阿吉                               |
| content     | string  | 用户评论                | 人民万岁                                |
| createdAt   | string  | 评论发送时间              | 2021-10-18T16:54:53.000Z            |
| status      | string  | 评论状态                | passed                              |
| activityId  | string  | 评论所在活动id            | 123456789                           |
| uid         | string  | 第三方用户唯一标识（需第三方登录定制） | 32733885                            |
| anonymousId | string  | session会话ID         | 867092dd                            |

## 返回示例

```
{
    "pager": {
        "page": 1,
        "pageSize": 20,
        "total": 1
    },
    "items": [
        {
            "userId": 123456789,
            "avatar": "http://hbimg.huabanimg.com/xxxxxxxxx-B6OFs4",
            "nickname": "没用的阿吉",
            "content": "人民万岁",
            "createdAt": "2021-10-18T16:54:53.000Z",
            "status": "passed",
            "activityId": "123456789",
            "uid": "00000",
            "anonymousId": "456132djk"
        }
    ]
}
```
