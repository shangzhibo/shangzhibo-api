## 评论清空（管理员）

### 接口

评论清空

```bash
DELETE /api/activity/{id}/comment
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

无需参数

### 响应

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| result | boolean |  |

#### 响应样例

```js
{
  "result": true,
}
```



