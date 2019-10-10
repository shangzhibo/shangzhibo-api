# 获取客户网站已授权用户信息

## 接口

```javascript
GET /api/v2/partner/user/profile?uid=xxx
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

以下参数需要在 query 中提供

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| uid | string | 唯一标识用户的 ID \(不论 uid 是数字类型还是字符串类型，都必须转为字符串\) | 是 |

### 请求示例:

```http
curl -H "Content-Type: application/json" -H "Authorization: Bearer <access_token>" http://shangzhibo.tv/api/v2/partner/user/profile?uid=xxx
```

## 响应 \(200\)

### 参数

| 参数 | 类型 | 参数说明 |
| :--- | :--- | :--- |
| result | boolean |  |
| user | object | 用户信息 |

#### user 参数内容:

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | integer | 主键 |
| uid | string | 唯一标识用户的 ID |
| nickname | string | 用户昵称（最长 45 位） |
| avatar | string | 用户头像 |
| sex | string | 用户性别\(male、female、unknown\) |
| country | string | 国家\(最大 20 位\) |
| province | string | 省份 \(最大 20 位\) |
| city | string | 城市 \(最大 20 位\) |
| createdAt | string | 创建时间 |
| updatedAt | string | 最后更新时间 |
| owner | integer | 其所属的AgentId |

### 响应示例:

```javascript
{
  "result":true,
  "user":{
    "id":95,
    "nickname":"xxxx",
    "sex":"male",
    "owner":233435,
    "uid":"xxx",
    "createdAt":"2019-10-09T03:04:23.000Z",
    "updatedAt":"2019-10-09T03:04:23.000Z"
  }
}
```

## 响应\(401\) 未认证

### 响应示例

```javascript
{
  "name":"Unauthorized",
  "message":"请提供正确有效的 access_token 值",
  "status":401
}
```

## 响应\(403\)

### 响应示例

```javascript
{
  "name":"Forbidden",
  "message":"无权访问该接口",
  "status":403
}
```

