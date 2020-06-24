---
description: 使用此功能前需要开通**用户明细**、**用户管理** 功能，同时还需要做第三方登录定制或进行微信服务号授权
---

# 获取指定用户的访问明细

## 接口

获取指定用户的访问明细

```javascript
GET /api/v3/agent/:id/user/:userId/stats/visits
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）。

注意：该功能需要第三方登录定制且开通 UID 白名单功能后才可以使用，具体请联系所属商务经理。

## 参数

| 参数       | 类型                                  | 参数位置  | 描述                                 | 是否必传 |
| :--------- | :------------------------------------ | :-------- | :----------------------------------- | :------- |
| id         | int                                   | url path  | 客户 id                              | 是       |
| userId     | int                                   | url path  | 客户所属用户 id                      | 是       |
| activityId | string                                | url query | 活动 id                              | 否       |
| page       | int                                   | url query | 当前页, 默认为 1                     | 否       |
| pageSize   | int                                   | url query | 每页返回个数，默认为 10，最大为 1000 | 否       |
| order      | enum&lt;visitAt asc, visitAt desc&gt; | url query | 排序方式, 默认为 visitAt desc        | 否       |

### 请求样例

```bash
curl 'shangzhibo.tv/api/v3/agent/105131/user/15460259/stats/visits?page=1&pageSize=10' \
  -H 'authorization: bearer <accessToken>'
```

## 响应

| 参数                | 类型    | 描述                                                                  |
| :------------------ | :------ | :-------------------------------------------------------------------- |
| pager               | object  | 分页信息                                                              |
| pager.page          | integer | 当前页                                                                |
| pager.pageSize      | integer | 每页返回个数                                                          |
| pager.total         | integer | 总个数                                                                |
| visitAt             | string  | 访问时间                                                              |
| lastOnlineAt        | string  | 最后在线时间                                                          |
| duration            | integer | 在线时长 (lastOnlineAt - visitAt), 单位分钟                           |
| userId              | integer | 用户 ID                                                               |
| activityId          | string  | 活动 ID                                                               |
| activity            | object  | 活动信息                                                              |
| activity.id         | string  | 活动 ID                                                               |
| activity.name       | string  | 活动名称                                                              |
| activity.categoryId | integer | 活动分类 ID                                                           |
| activity.status     | string  | 活动状态，enabled 允许推流 disabled 禁止推流 forbidden 管理员禁止推流 |
| activity.agentId    | integer | 账号 ID                                                               |
| activity.startedAt  | string  | 活动开始时间                                                          |
| activity.endedAt    | string  | 活动结束时间                                                          |
| activity.pushDomain | string  | 推流域名                                                              |
| activity.pullDomain | string  | 拉流域名                                                              |
| activity.isPushing  | boolean | 是否在推流                                                            |
| activity.createdAt  | string  | 活动创建时间                                                          |
| activity.groupId    | integer | 活动分组 ID                                                           |
| activity.updateAt   | string  | 活动更新时间                                                          |

```javascript
{
    "pager":{
        "page":1,
        "pageSize":10,
        "total":2
    },
    "items":[{
            "activity":{
                "isArchived":false,
                "isPushing":false,
                "id":"10096289",
                "agentId":105131,
                "subagentId":null,
                "categoryId":1,
                "name":"这是一场直播",
                "status":"disabled",
                "startedAt":"2020-06-24T00:00:00.000Z",
                "endedAt":"2020-06-24T05:36:51.878Z",
                "pushDomain":"push.shangzhibo.tv",
                "pullDomain":"play.shangzhibo.tv",
                "groupId":-1,
                "createdAt":"2020-06-22T03:06:29.000Z",
                "updatedAt":"2020-06-24T05:37:26.322Z"
            },
            "visitAt":"2020-06-24T04:28:02.000Z",
            "lastOnlineAt":"2020-06-24T04:28:05.000Z",
            "duration":0,
            "userId":15460259,
            "activityId":"10096289"
        }, {
            "activity":{
                "isArchived":false,
                "isPushing":false,
                "id":"10096289",
                "agentId":105131,
                "subagentId":null,
                "categoryId":1,
                "name":"这是一场直播",
                "status":"disabled",
                "startedAt":"2020-06-24T00:00:00.000Z",
                "endedAt":"2020-06-24T05:36:51.878Z",
                "pushDomain":"push.shangzhibo.tv",
                "pullDomain":"play.shangzhibo.tv",
                "groupId":-1,
                "createdAt":"2020-06-22T03:06:29.000Z",
                "updatedAt":"2020-06-24T05:37:26.322Z"
            },
            "visitAt":"2020-06-24T01:40:01.000Z",
            "lastOnlineAt":"2020-06-24T01:44:04.000Z",
            "duration":4,
            "userId":15460259,
            "activityId":"10096289"
        }]
}
```
