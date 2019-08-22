## 修改授权

### 接口

修改微信登录授权

```js
PUT /api/activity/{id}/auth
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| --- | --- | --- | --- |
| methods | array | 授权观看的方式 | 是 |

#### 微信登录授权请求样例

```js
{
  "methods": [["wechat"]]
}
```

#### 关闭微信登录授权请求样例

```js
{
  "methods": []
}
```

### 响应

#### 响应样例

```js
{
  "result": true
}
```



