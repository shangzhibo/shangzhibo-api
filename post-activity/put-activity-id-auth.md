# 修改授权

## 接口

修改授权

```javascript
PUT /api/activity/{id}/auth
```

## 授权

请求 header

```text
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| methods | array | 授权观看的方式 | 是 |

### 微信登录授权请求样例

```javascript
{
  "methods": [["wechat"]]
}
```

### 关闭微信登录授权请求样例

```javascript
{
  "methods": []
}
```

## 响应

### 响应样例

```javascript
{
  "result": true
}
```

