# 修改自定义菜单配置

## 接口

修改自定义菜单配置

```javascript
 PUT /api/activity/:id/menu
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 请求

以下内容在 body 中提供

#### menu 参数内容:

| 参数 | 参数类型 | 参数说明 | 是否必要 |
| :--- | :--- | :--- | :--- |
| title | string | 标题 | 是 |
| url | string | 图片内容 对应的图片 url | 否 |
| productList | array | 商品列表 | 否 |
| richText | string | 图文内容对应的富文本 | 否 |
| hyperLink | string | 菜单跳转对应的 url | 否 |
| chatRoom | boolean | 聊天室状态 | 是且必须为 true |
| topGift | boolean | 是否打开礼物打赏排行榜开关 | 否 |
| topShare | boolean | 是否打开分享榜单排行榜开关 | 否 |

**productList 参数内容**

| 参数 | 参数类型 | 参数说明 | 是否必要 |
| :--- | :--- | :--- | :--- |
| name | string | 商品名称 | 是 |
| image | string | 商品图片链接 | 是 |
| price | number | 商品价格 | 是 |
| button | string | 按钮文案 | 是 |
| link | string | 商品链接地址 | 是 |

### 请求示例:

```http
curl -H "Content-Type: application/json" -H "Authorization: Bearer <access_token>" -X "PUT" http://shangzhibo.tv/api/activity/:id/menu -d $'[{"title":"聊天室","chatRoom":true},{"title":"活动简介","richText":"<p>测 试一下</p>"},{"title":"菜单名称","productList":[{"name":"啦啦啦","image":"https://doc.shangzhibo.tv/client/user/105131/1570765196725/1570765196692_NorthernLightsandNoctilucentCloudsNASAAstronomyPictureoftheDay.jpg","price":12,"button":"LaLa","link":"http://shangzhibo.tv"}]}]'
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

## 响应\(401\)

body 参数不能为空

```javascript
{
    "name":"BadRequest",
    "message":"The menu can't be empty",
    "status":400
}
```

### 响应\(403\)

chatRoom 选项不能为 false

```javascript
{
    "name":"Forbidden",
    "message":"Chat room can't be closed",
    "status":403
}
```

