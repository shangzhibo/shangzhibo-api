## 获取活动列表

### 接口

请求地址

```
GET api/activity
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数 | 参数类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| isArchived | boolean | 否 | “true“ 表示已归档，“false” 表示未归档 |
| name | string | 否 | 活动名称 |
| isPushing | boolean | 否 | 是否处于推流状态 |
| orderBy | string | 否 | 支持排序的字段：\`createdAt\`, \`endedAt\` , \`startedAt\` ；可按正序（ASC）或者倒序（DESC）来排，比如：\`createdAt DESC\`  表示按照创建时间倒序排 |
| page | integer | 否 | 页码 |
| pageSize | integer | 否 | 每页几条 |

### 请求样例

```
/api/activity?isArchived=false&page=42&pageSize=42
```

### 响应参数

| 参数 | 类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| page | string | 页码 | 2 |
| pageSize | string | 一页显示几条 | 10 |
| total | string | 总条数 | 100 |
| id | string | 活动 ID | 8050309 |
| name | string | 活动名称 | 分享禁用测试活动 |
| status | string | 活动状态 | enabled |

### 响应示例

```js
{
    "pager": {
        "page": 1,
        "pageSize": 10,
        "total": 16
    },
    "items": [
        {
            "id": "2837888",
            "name": "创想人工智能峰会-深圳站",
            "categoryId": 1,
            "status": "disabled",
            "agentId": 101691,
            "startedAt": "2018-01-29T06:58:26.000Z",
            "endedAt": "2018-01-29T10:58:26.000Z",
            "pushDomain": "push.shangzhibo.tv",
            "pullDomain": "play.shangzhibo.tv",
            "isPushing": false,
            "createdAt": "2018-01-29T05:58:28.000Z",
            "updatedAt": "2018-01-29T11:09:35.000Z",
            "app": "r1g3-d43BM",
            "stream": "Hkb3WOE2BM",
            "isPrologueEnabled": true,
            "isEpilogueEnabled": true,
            "isLiveEnabled": true,
            "fake": {
                "baseCount": 0,
                "increaseMin": 1,
                "increaseMax": 1
            },
            "isFakeEnabled": false,
            "isFilterAllEnabled": false,
            "filterIpList": {},
            "filterSidList": {},
            "filterUserList": {},
            "isRobotEnabled": false,
            "robot": {
                "initialCount": 10,
                "incrementCount": 1
            },
            "expired": false,
            "maxConcurrentUser": -1,
            "maxPushingTime": -1
        }
    ]
}
```



