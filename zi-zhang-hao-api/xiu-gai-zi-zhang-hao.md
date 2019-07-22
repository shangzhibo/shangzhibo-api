# 修改子账号

## 接口

创建子账号

```javascript
PUT api/agent/subagent
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数 | 参数类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| username | string | 是 | 用户名，如：手机号/邮箱 |
| password | string | 是 | 密码，限制 6-64 位 |
| remark | string | 否 | 子账号备注 |
| activities | array&lt;string&gt; | 否 | 活动 ID 集合，如：\['1', '2', '3'\] |

## 请求样例

```text
/api/agent/subagent
```

## 响应示例

```javascript
{
  "result": true,
}
```

