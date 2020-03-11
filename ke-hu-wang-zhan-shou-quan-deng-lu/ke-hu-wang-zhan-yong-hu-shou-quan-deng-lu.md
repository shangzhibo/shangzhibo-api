# 客户网站用户授权\(同步用户标识\)

## 接口

```http
POST /api/v2/partner/user/login
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

以下参数需要在 body 中提供

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| uid | string | 唯一标识用户的 ID \(不论 uid 是数字类型还是字符串类型，都必须转为字符串\) | 是 |
| cookieId | string | 为每个访客在 cookie 中生成的唯一标识（par.shangzhibo.sid） | 是 |

### 请求示例:

```http
curl -H "Content-Type: application/json" -H "Authorization: Bearer <access_token>" -X "POST" http://shangzhibo.tv/api/v2/partner/user/login -d $'{"uid":"xxxx","cookieId":"xxxxx"}'
```

## 用户数据标识同步完成后，需要开发者将 cookieId（假设为 123456789） 传递到上直播在进行访问

### 标识已同步用户请求示例

```http
curl -H "Content-Type: application/json" -b 'par.shangzhibo.sid=123456789' "http://<自定义域名>/watch/:id"
```

### 特殊情况说明

APP 环境或者未定制上直播播放域名的客户可能无法使用 cookie（`par.shangzhibo.sid`） 方式，此时可以将访客唯一标识通过播放页 URL 后加参数带过来。

`http://<自定义域名>/watch/{activityId}?parSid=xxxxx`

并将 parSid 仍通过本接口 cookieId 字段传给上直播。

如果参数里面含有特殊字符（如：`+` 、`/` 等在 URL具有含义的字符） 需要对参数进行 URI encode。

```javascript
let parSid = 'rcTDGfQv7p8P+g//DZ0wFQ=='
parSid = encodeURIComponent(parSid)
// parSid === 'rcTDGfQv7p8P%2Bg%2F%2FDZ0wFQ%3D%3D'
```

```http
curl -H "Content-Type: application/json" "http://<自定义域名>/watch/:id?parSid=123456789"
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

## 响应\(404\)

### 响应示例

```javascript
{
  "name":"NotFound",
  "message":"User Not Found",
  "status":404
}
```

