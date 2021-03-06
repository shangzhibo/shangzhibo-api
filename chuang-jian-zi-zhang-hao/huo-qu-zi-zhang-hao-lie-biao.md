# 获取子账号列表

## 接口

创建子账号

```javascript
GET api/agent/subagent
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 请求样例

```text
/api/agent/subagent
```

## 响应参数

| 参数 | 参数类型 | 描述 |
| :--- | :--- | :--- |
| id | string | 子账号id |
| username | string | 用户名，如：手机号/邮箱 |
| remark | string | 子账号备注 |
| activities | array&lt;string&gt; | 活动 ID 集合，如：\['1', '2', '3'\] |
| createdAt | string | 创建时间 |
| updateAt | string | 最后更新时间 |

## 响应示例

```javascript
[
    {
        "activities": [
            "2268308",
            "3791930",
            "2738667"
        ],
        "id": 191,
        "username": "15956387658",
        "remark": "灵",
        "createdAt": "2019-03-12T01:55:09.000Z",
        "updatedAt": "2019-07-16T06:03:46.000Z",
    }
]
```

