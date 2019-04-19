## 获取指定活动原始文档地址列表

### 接口

获取文档列表信息

```js
GET /api/activity/{id}/doc
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

无

#### 请求样例

```js
/api/activity/8930091/doc
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| name | string | 文档原始文件名 |
| url | string | 文档原始文件地址 |

#### 响应样例

```json
[
    {
        "name": "test.pptx",
        "url": "https://shangzhibo-img.b0.upaiyun.com/client/activity/2929745/doc/1555639340325/229c988d45ce0222bd5e710056a58de7.pptx"
    },
    {
        "name": "test.pptx",
        "url": "https://shangzhibo-img.b0.upaiyun.com/client/activity/2929745/doc/1555640375918/229c988d45ce0222bd5e710056a58de7.pptx"
    }
]
```



