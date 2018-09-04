## 回传订单数据

### 接口

回传订单数据

```js
POST /api/callback/pay
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
| identity | string | 厂商标识 | 是 |
| uid | integer | 唯一标识用户的 ID | 是 |
| activityId | string | 付费频道 ID | 是 |
| orderId | string | 订单 ID | 是 |
| price | number | 订单价格 | 是 |

#### 请求样例

```js
{
  "identity": "shangzhibo",
  "uid": 2580821,
  "activityId": "5098710",
  "orderId": "2017033023143744487514",
  "price": 9.9
}
```

### 响应

#### 响应样例

```js
{
  "result": true,
}
```



