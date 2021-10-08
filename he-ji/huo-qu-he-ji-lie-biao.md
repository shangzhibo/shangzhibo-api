# 获取合辑列表

## 接口

请求地址

```text
GET /api/v3/catalog
```

## 授权

请求**header**

```text
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注: 请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| page | integer | 页数\(默认第一页，最小为1\) | 否 |
| pageSize | integer | 每页显示数量\(默认10，最小为0\) | 否 |
| order | string | 排序方式\(默认： 'id desc' \) | 否 |

## 请求样例

```text
GET /api/v3/catalog?page=1&pageSize=5&order=id desc
```

## 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| **pager** | object |  |
| pager.page | integer | 当前页 |
| pager.pageSize | integer | 每页返回数量 |
| pager.total | integer | 合辑总量 |
| **items** | array&lt;object&gt; | 合辑明细 |
| **chapter** | array&lt;object&gt; | 合辑章节 |
| chapter.selection | string | 章节名称 |
| chapter.activityIds | array&lt;string&gt; | 活动ID列表 |
| **chapter.activities** | array&lt;object&gt; | 活动内容 |
| chapter.activities.id | string | 活动ID |
| chapter.activities.name | string | 活动名称 |
| chapter.activities.isPushing | boolean | 是否正在推流 |
| chapter.activities.imgCover | string | 活动封面 |
| chapter.activities.link | string | 活动链接 |
| chapter.activities.type | string | 活动类型\(**枚举值\[ '**live'：直播；'video'：视频\]\) |
| chapter.activities.startedAt | string | 开始时间 |
| chapter.activities.endedAt | string | 结束时间 |
| id | integer | 合辑ID |
| agentId | integer | 客户ID |
| name | string | 合辑名称 |
| createdAt | string | 创建时间 |
| updatedAt | string | 更新时间 |
| **appearance** | object | 界面配置 |
| appearance.cover | string |  |
| **abstract** | object | 简介信息 |
| abstract.richText | string | html |
| **share** | object | 分享配置 |
| share.title | string |  |
| **share.wechat** | object |  |
| share.wechat.text | string |  |
| share.wechat.image | string |  |
| **share.wechatZone** | object |  |
| share.wechatZone.text | string |  |
| share.wechatZone.image | string |  |
| link | string | 合辑页面地址 |

## 响应示例

```text
{
    "pager": {
        "page": 1,
        "pageSize": 5,
        "total": 1
    },
    "items": [
        {
            "chapters": [
                {
                    "selection": "",
                    "activityIds": [
                        "xxxxxxxx",
                        "xxxxxxxx",
                    ],
                    "activities": [
                        {
                            "id": "xxxxxxxx",
                            "name": "emma",
                            "isPushing": false,
                            "type": "video",
                            "startedAt": "2098-12-31T16:00:00.000Z",
                            "endedAt": "2222-08-25T12:05:00.000Z",
                            "imgCover": "https://doc.shangzhibo.tv/resources/xxxxxx/xxxxxxxx/asdasdasdas.jpeg",
                            "link": "http://shangzhibo.tv/watch/xxxxxxxx"
                        },
                        {
                            "id": "xxxxxxxx",
                            "name": "waston",
                            "isPushing": false,
                            "type": "live",
                            "startedAt": "2021-09-07T06:05:00.000Z",
                            "endedAt": "2021-09-08T06:05:00.000Z",
                            "imgCover": "https://doc.shangzhibo.tv/resources/xxxxxx/xxxxxxxx/asdasdasd.jpeg",
                            "link": "http://shangzhibo.tv/watch/xxxxxxxx"
                        }
                    ]
                }
            ],
            "id": xxx,
            "agentId": xxxxxx,
            "name": "share",
            "createdAt": "2021-08-26T09:51:06.000Z",
            "updatedAt": "2021-09-09T02:31:21.000Z",
            "appearance": {
                "cover": "https://doc.shangzhibo.tv/resources/xxxxxx/fdsfdsfds.jpeg"
            },
            "abstract": {},
            "share": {
                "title": "share",
                "wechat": {
                    "text": "",
                    "image": "https://doc.shangzhibo.tv/system/activity/template/default-share-img.png"
                },
                "wechatZone": {
                    "text": "",
                    "image": "https://doc.shangzhibo.tv/system/activity/template/default-share-img.png"
                }
            },
            "link": "http://shangzhibo.tv/w/catalog/xxx"
        }
    ]
}
```

