# 获取活动分组

### 接口

获取活动分组

```bash
GET /api/agent/activity-group
```

### 授权

```yaml
Authorization: Bearer <accessToken>
Content-Type: application/json
```

> 注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

### 参数

| 参数 | 参数类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| name | string | 否 | 传递则通过传递的字符串模糊匹配分组名称 |

### 响应200

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
|  | array&lt;object&gt; |  |
| id | integer | 分组 ID |
| agentId | integer | 客户 ID |
| name | string | 分组名称 |
| createdAt | string | 创建时间 |
| updatedAt | string | 更新时间 |

### 响应样例

```javascript
[
    {
        "id": 1,
        "agentId": 1001,
        "name": "分类1",
        "createdAt": "2020-09-15T07:21:20.000Z",
        "updatedAt": "2020-09-15T07:21:23.000Z"
    }
]
```





