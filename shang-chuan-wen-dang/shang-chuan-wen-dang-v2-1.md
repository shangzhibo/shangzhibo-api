# 上传文档 V2

## 接口

上传文档, 支持的文件后缀: doc、docx、pdf、ppt、pptx

```javascript
POST /api/v2/activity/:id/doc
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: multipart/form-data
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

无

## 请求样例

```bash
curl -H "Authorization: bearer <Access Token>" "http://shangzhibo.tv/api/v2/activity/:id/doc" -F file=@raft.pdf
```

### 文件上传示例代码:

```markup
<html>
    <form name="form" action="https://shangzhibo.tv/api/v2/activity/12345678/doc" method="POST" enctype ="multipart/form-data">
        <input type="file" name="filename">
        <input type="submit" value="submit">
    </form>
</html>
```

## 响应 200

HTTP/1.1 200 OK

### 响应样例

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| taskId | string | 转码任务 id，用于查询文档转码进度 |

```javascript
{
    "taskId":"ef141163-2572-49fe-951a-1501cb7ce914"
}
```

## 响应 400

```javascript
// 文档文件最大为 40MB
{
    "name":"BadRequest",
    "message":"文件大小超过限制",
    "status":400
}

// 文档只支持 pdf, ppt, word 三种，对应的后缀为 pdf, pptx, ppt, doc, docx
{
    "name":"BadRequest",
    "message":"不支持的文件类型",
    "status":400
}

// 每个请求文档上传数量限制为 1 个
{
      "name": 'BadRequest',
      "message": ' 一次最多只能传一个文件',
      "status": 400,
}
```

## 响应 429

```javascript
{
    "name":"TooManyRequests",
    "message":"请求速度太频繁了, 请于xxx后重试",
    "status":429
}
```

