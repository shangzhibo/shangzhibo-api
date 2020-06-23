# 删除子账号

## 接口

创建子账号

```javascript
DELETE api/agent/subagent/{id}
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 请求样例

```http
/api/agent/subagent/191
```

## 响应示例

```javascript
{
  "result": true,
}
```

