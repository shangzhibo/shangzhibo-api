## 获取指定活动登录观众列表

### 接口

获取登录观众列表

```
GET /api/activity/{id}/user
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
/api/activity/{id}/pay?page=42&pageSize=42
```

### 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| id | integer | 上直播观众 id |
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
        "id": 737961,
        "nickname": "鹿大大",
        "sex": "male",
        "province": "Zhejiang",
        "city": "Hangzhou",
        "country": "China",
        "avatar": "http://wx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTKdTOKORMFGGUgib8thbKENnzZtpy0iabWcdVkh9eiaK9Ros4tcJtE88babelA7VuibGWbheFOmhd9Mxw/132",
        "wechatId": "oqaFLxDTwQTN2Hxlz_VcrW2-mA64",
        "createdAt": "2017-11-28T04:01:14.000Z",
        "updatedAt": "2018-01-11T12:03:21.000Z",
        "agentId": null,
        "identity": null,
        "uid": null
    }
]
```



