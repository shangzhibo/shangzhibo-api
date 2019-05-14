# 获取指定活动付费观看记录

## 接口

获取付费观看记录

```javascript
GET /api/activity/{id}/pay
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| page | integer | 页码 | 是 |
| pageSize | integer | 每页几条 | 是 |

## 请求样例

```text
/api/activity/{id}/pay?page=42
```

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| page | integer | 页码 |
| pageSize | integer | 每页几条 |
| total | integer | 总条数 |
| totalCount | number | 支付总额 |
| id | integer | 上直播观众 id |
| nickname | string | 从微信获取的观众昵称 |
| sex | string | 从微信获取的观众性别 |
| province | string | 从微信获取的观众所在省份 |
| city | string | 从微信获取的观众所在城市 |
| country | string | 从微信获取的观众所在国家 |
| avatar | string | 从微信获取的观众头像 |
| wechatId | string | 微信 id |
| agentId | integer | 上直播账号 id（管理员 id） |
| createdAt | string | 付费时间 |
| updatedAt | string | 更新时间 |

## 响应示例

```text
{
    "pager": {
        "total": 1,
        "page": 1,
        "pageSize": 10
    },
    "totalCount": 9.90,
    "items": [
        {
            "userId": 737961,
            "paid": 9.90,
            "createdAt": "2018-02-07T07:49:41.000Z",
            "updatedAt": "2018-02-07T07:49:50.000Z",
            "user": {
                "nickname": "鹿大大",
                "avatar": "http://wx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTKdTOKORMFGGUgib8thbKENnzZtpy0iabWcdVkh9eiaK9Ros4tcJtE88babelA7VuibGWbheFOmhd9Mxw/132"
            }
        }
    ]
}
```

