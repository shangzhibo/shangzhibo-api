## 账号体系对接

### 接口
账号体系对接

```js
POST /api/callback/account
```
### 授权
请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数        | 参数类型     | 参数说明   | 是否必填 |
| --------- | -------- | ------ | ---- |
| sid      | string   | Session ID  | 是    |
| mobile | string | 手机号 | 是    |
| nickname | string | 昵称 | 否    |
| avatar | string | 头像图片 | 否    |
| city | string | 城市 | 否    |
| country | string | 国家 | 否    |
| sex | string | 性别 | 否    |
| wechat | object | 微信登录信息 | 微信登录回调时需要    |

#### wechat 参数

| 参数        | 参数类型     | 参数说明   | 是否必填 |
| --------- | -------- | ------ | ---- |
| openid | string | 登录 openid | 是    |
| unionid  | string | 只有在用户将公众号绑定到微信开放平台帐号后，才会出现该字段  | 否    |


#### 请求样例

```js
{
  "sid": "哈哈哈",
  "mobile": "18638777777",
  "nickname": "羊."
  "avatar": "http://image.com/image.png"
  "city": "Hangzhou"
  "province": "Zhejiang"
  "country": "China"
  "sex": "male"
  "wechat": {
    "openid": "o-jJOw_Q4ZGH16dgPg8olwW_-v-Q ovmel0mA9ux61sqciW5QUWGYc1MQ"
    "unionid": "oWjUrwtLzIRoowC14GxMYGw6mapQ"
  }
}
```

### 响应

#### 响应样例
```js
{
    "result": true,
}
```


