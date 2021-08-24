---
description: 需要联系商务开通用户明细功能
---

# 获取指定活动的用户观看明细

## 接口

获取用户观看明细列表

```javascript
GET /api/activity/:id/stats/user-visits
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| page | integer | 页数（默认第一页） | 否 |
| pageSize | integer | 每页显示数量（默认 10） | 否 |
| startedAt | string | 查询开始时间 | 否 |
| endedAt | string | 查询截止时间（最多支持查询 7 天范围内的数据） | 否 |

注：查询的时间采用**格林尼治标准时间**，格式为：`2019-06-21T01:52:12.736Z`

## 请求样例

```text
GET /api/activity/<活动Id>/stats/user-visits
```

## 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| pager | object |  |
| pager.page | integer | 当前页 |
| pager.pageSize | integer | 每页返回数量 |
| pager.total | integer | 明细总量 |
| items | array&lt;object&gt; | 明细列表 |
| userId | null 或 integer | 用户 Id，**匿名用户此处为空** |
| province | string | 省份 |
| city | string | 城市 |
| visitAt | string | 访问时间 |
| lastOnlineAt | string | 最后在线时间 |
| duration | integer | 在线时长（单位**分钟**） |
| referer | string | 用户来源 |
| userAgent | string | 浏览器 ua |
| device | string | 访问设备 |
| nickname | string | 用户名称, 默认为 **匿名用户** |
| avatar | string | 用户头像，默认为 **空字符串** |
| anonymousId | string | session id 前8位 \(仅限**匿名用户**\) |
| partnerUID | string | 第三方登录用户 id ，默认为**空字符串**，需要开通**第三方登录功能** |
| invitedBy | integer | 用户邀请人 id_**（该字段是用户级别的，并不是本次活动的邀请人）**_ |

## 响应示例

```javascript
{
    "pager":{
        "page":1,
        "pageSize":15,
        "total":1
    },
    "items":[
        {
            "userId":2184958,
            "province":"浙江",
            "city":"杭州",
            "visitAt":"2020-03-31T08:21:00.000Z",
            "lastOnlineAt":"2020-03-31T08:21:03.000Z",
            "duration":0,
            "referer":"https://shangzhibo.tv/watch/10024069",
            "userAgent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.149 Safari/537.36",
            "device":"Mac OS",
            "nickname":"测试",
            "avatar":"http://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTJdhX8EJDyyxX3NHRRqu30ia6ibCdft438GpiayNiaO2NYoKxiaCQCQIx0GMu3CKvN0jHu1lzNWufaS9ibA/132",
            "anonymousId":"",
            "partnerUID":""
        }
    ]
}
```

