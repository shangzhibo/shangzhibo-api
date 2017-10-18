## 账号体系对接

### 接口
账号体系对接

```js
POST /api/callback/user
```
### 授权
请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数       | 参数类型   | 参数说明          | 是否必填 |
| -------- | ------ | ------------- | ---- |
| unionid  | string | 微信用户的 unionid | 是    |
| nickname | string | 用户微信昵称        | 是    |
| avatar   | string | 用户微信头像        | 是    |
| sex      | string | 用户性别          | 是    |
| country  | string | 国家            | 否    |
| province | string | 省份            | 否    |
| city     | string | 城市            | 否    |

#### 请求样例

```js
{
  "unionid": "oWjUrwtLzIRoowC14GxMYGw6mapQ",
  "nickname": "兰海ena",
  "avatar": "http://static.itdks.com/files/default/2017/09-28/17403642672f970434.jpg",
  "sex": "male",
  "country": "China",
  "province": "Zhejiang",
  "city": "Hangzhou"
}
```

### 响应

#### 响应样例
```js
{
  "result": true,
}
```


