# 获取自定义菜单配置

## 接口

获取自定义菜单配置

```javascript
GET /api/activity/:id/menu
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

### 请求示例:

```http
curl -H "Content-Type: application/json" -H "Authorization: Bearer <access_token>" http://shangzhibo.tv/api/activity/:id/menu
```

## 响应 \(200\)

### 参数

| 参数 | 类型 | 参数说明 |
| :--- | :--- | :--- |
| result | boolean |  |
| menu | array | 自定义菜单信息 |

#### menu 参数内容:

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| title | string | 标题 |
| url | string | 图片内容 对应的图片 url |
| productList | array | 商品列表 |
| richText | string | 图文内容对应的富文本 |
| hyperLink | string | 菜单跳转对应的 url |
| chatRoom | boolean | 聊天室状态 |
| topGift | boolean | 是否打开礼物打赏排行榜开关 |
| topShare | boolean | 是否打开分享榜单排行榜开关 |

**productList 参数内容**

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| name | string | 商品名称 |
| image | string | 商品图片链接 |
| price | number | 商品价格 |
| button | string | 按钮文案 |
| link | string | 商品链接地址 |

### 响应示例1:

```javascript
{
    "result":true,
    "menu":[
        {
            "title":"聊天室",
            "chatRoom":true
        },
        {
            "title":"活动简介",
            "richText":""
        }
    ]
}
```

### 响应示例 2:

```javascript
{
    "result":true,
    "menu":[
        {
            "title":"聊天室",
            "chatRoom":true
        },
        {
            "title":"活动简介",
            "richText":"<p>测试一下</p>"
        },
        {
            "title":"菜单名称",
            "productList":[
                {
                    "name":"啦啦啦",
                    "image":"https://doc.shangzhibo.tv/client/user/105131/1570764238698/1570764238659_kumo.jpg",
                    "price":123,
                    "button":"啦啦啦",
                    "link":"http://shangzhibo.tv"
                }
            ]
        }
    ]
}
```

