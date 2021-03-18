# 获取聚合页列表\(new\)

## 接口

```text
GET /api/page
```

## 授权

```text
Authorization: Bearer <accessToken>
Content-Type: application/json
```

> 注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| page | integer | 否 | 当前页数 |
| pageSize | integer | 否 | 每页条数 |
| orderBy | string | 否 | 根据创建时间排序 |

```text
GET /api/page?page=1&pageSize=10&orderBy=createdAt DESC
```

## 响应参数

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | string | 门户页id |
| agentId | integer | 客户id |
| title | string | 门户标题 |
| data | object | 门户样式 |

## 响应示例

```text
{
    "pager": {
        "page": 1,
        "pageSize": 10,
        "total": 1
    },

    "items": [
        {
            "id": "zXB1A5IvxNw",
            "agentId": 120489,
            "title": "门户",
            "data": {
                "moreActivity": {
                    "showMoreActivity": false,
                    "checkTab": 0
                },
                "isMobileNavEnabled": true,
                "isHeaderNavEdited": false,
                "title": "门户",
                "header": {
                    "logo": "",
                    "nav": [
                        {
                            "name": "导航一",
                            "link": "http://example.com",
                            "target": true
                        },
                        {
                            "name": "导航二",
                            "link": "http://example.com",
                            "target": true
                        },
                        {
                            "name": "导航三",
                            "link": "http://example.com",
                            "target": true
                        },
                        {
                            "name": "导航四",
                            "link": "http://example.com",
                            "target": true
                        }
                    ]
                },
                
                "banner": [
                    {
                        "image": "//doc.shangzhibo.tv/tmp/live_banner.jpg",
                        "title": "企业门户标题",
                        "subtitle": "这里填写企业门户副标题",
                        "desc": "这里可以填写相关的表述，简单介绍企业门户内容",
                        "link": {
                            "show": true,
                            "src": "http://example.com",
                            "text": "查看"
                        },
                        "imageLink": "http://example.com",
                        "center": false
                    }
                ],
                "mobilesNav": [
                    {
                        "name": "导航1",
                        "src": "//doc.shangzhibo.tv/tmp/live_banner.jpg",
                        "url": "http://example.com",
                        "blank": true
                    },
                    {
                        "name": "导航2",
                        "src": "//doc.shangzhibo.tv/tmp/live_banner.jpg",
                        "url": "http://example.com",
                        "blank": true
                    },
                    {
                        "name": "导航3",
                        "src": "//doc.shangzhibo.tv/tmp/live_banner.jpg",
                        "url": "http://example.com",
                        "blank": true
                    },
                    {
                        "name": "导航4",
                        "src": "//doc.shangzhibo.tv/tmp/live_banner.jpg",
                        "url": "http://example.com",
                        "blank": true
                    }
                ],
                
                "main": {
                    "hotActivities": {
                        "show": true,
                        "num": 3
                    },
                    "newActivities": {
                        "show": true,
                        "num": 3
                    }
                },
                
                "contents": [
                    {
                        "show": true,
                        "layout": "line",
                        "card": "vertical",
                        "type": "activities",
                        "data": {
                            "hotActivities": {
                                "show": true,
                                "num": 6
                            },
                            "newActivities": {
                                "show": true,
                                "num": 6
                            },
                            "listIds": [],
                            "cardIds": []
                        }
                    },
                    {
                        "show": false,
                        "layout": "tab",
                        "card": "horizontal",
                        "type": "cards",
                        "data": {
                            "hotActivities": {
                                "show": false,
                                "num": 6
                            },
                            "newActivities": {
                                "show": false,
                                "num": 6
                            },
                            "listIds": []
                        }
                    },
                    {
                        "show": false,
                        "layout": "tab",
                        "card": "horizontal",
                        "type": "cards",
                        "data": {
                            "hotActivities": {
                                "show": false,
                                "num": 6
                            },
                            "newActivities": {
                                "show": false,
                                "num": 6
                            },
                            "listIds": []
                        }
                    }
                ],
                
                "slogan": {
                    "show": true,
                    "logo": "",
                    "desc": ""
                },
                
                "footer": {
                    "show": true,
                    "text": "Shangzhibo.tv",
                    "link": "shangzhibo.tv"
                },
                "share": {}
            },
            "createdAt": "2020-08-04T06:25:24.000Z",
            "updatedAt": "2020-08-04T06:25:28.000Z"
        }
    ]
}
```





