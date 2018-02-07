## 获取指定活动的登录观众列表

### 接口

获取付费观看记录

```
GET /activity/{id}/pay
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

无

### 请求样例

```
/activity/{id}/pay?page=42&pageSize=42
```

### 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| id | integer | 从微信获取的观众 id |
| nickname | string | 从微信获取的观众昵称 |
| sex | string | 从微信获取的观众性别 |
| province | string | 从微信获取的观众所在省份 |
| city | string | 从微信获取的观众所在城市 |
| country | string | 从微信获取的观众所在国家 |
| avatar | string | 从微信获取的观众头像 |
| wechatId | string | 微信 id |
| createdAt | string | 付费时间 |
| updatedAt | string | 更新时间 |

### 响应示例

```
[
  {
    "id": 42,
    "nickname": "stringValue",
    "sex": "male",
    "province": "stringValue",
    "city": "stringValue",
    "country": "stringValue",
    "avatar": "stringValue",
    "wechatId": "stringValue",
    "createdAt": "stringValue",
    "updatedAt": "stringValue"
  }
]
```

  


