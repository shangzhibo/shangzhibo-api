# 获取原始文档地址列表

## 接口

获取文档列表信息

```javascript
GET /api/v2/activity/:id/doc/:docd
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

无

### 请求样例

```javascript
/api/v2/activity/:id/doc/:docId
```

## 响应

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | integer | 文档 Id |
| name | string | 文档原始文件名 |
| url | string | 文档原始文件地址 |
| activityId | string | 活动 Id |
| index | integer | 当前文档页面索引 |
| status | string | 转码状态 |
| taskId | string | 转码任务 Id |
| url | string | 文档原始地址 |
| pages | array | 文档转码后的输出文件，即文档单页 |
| pageCount | integer | 文档总页数 |

### 响应样例

```javascript
{
    "id":2276, // 文档 Id
    "activityId":"12345678", // 活动 Id
    "index":3, // 当前文档页面索引
    "status":"finished", // 转码状态
    "taskId":"8a783a29-0a63-4b11-aa47-7bb906692a50", // 转码任务 Id
    "name":"raft.pdf", // 文档名称
    "url":"https://office.shangzhibo.tv/105131/12345678/1561700366504/176afec0-9967-11e9-901e-b90909ae0323.pdf", // 文档原始地址
    "pages":[ // 文档转码后的输出文件，即文档单页
        "https://office.shangzhibo.tv/105131/12345678/1561700366504/176afec0-9967-11e9-901e-b90909ae0323-1.jpg",
        ...,
        "https://office.shangzhibo.tv/105131/12345678/1561700366504/176afec0-9967-11e9-901e-b90909ae0323-18.jpg"
    ],
    "pageCount":18 // 文档总页数
}
```

