# 修改指定活动信息

## 接口

修改活动

```javascript
PUT /api/activity/:id
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
| name | string | 活动名称 | 否 |
| isArchived | boolean | “true”表示已归档，“false”表示未归档 | 否 |
| startedAt | datetime | 直播开始时间 | 否 |
| endedAt | datetime | 直播结束时间 | 否 |
| subagentIds | Array&lt;Integer&gt; | 子账号 Id 集合 | 否 |
| groupId | integer | 活动分组 Id, 默认为-1，即不指定分组 | 否 |

### 请求样例

```javascript
{
  "name": "直播测试",
  "startedAt": "2016-11-08T12:00:00.000Z",
  "endedAt": "2016-11-08T13:00:00.000Z",
  "isArchived": true,
  "subagentIds": [1, 2]
}
```

### 响应样例200

```javascript
{
  "result": true
}
```

