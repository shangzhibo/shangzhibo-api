# 查看文档转码状态 V2

## 接口

```javascript
GET /v2/activity/:id/doc
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :---|
| taskId | string| 文档转码任务 id | 是 |

### 请求样例

```bash
curl -H "Authorization: bearer <Access Token>" "https://shangzhibo.tv/api/v2/activity/:id/doc?taskId=ef141163-2572-49fe-951a-1501cb7ce914"
```

## 响应

### 响应样例

```javascript
// 转码成功:
{
    "status": "finished"
}

// 正在转码:
{
    "status": "running"
}

// 转码失败:
{
    "status": "failed"，
    "errorCode": "xxxxxxx"
}

errorCode 错误码:
  NoError: 没发生错误
  ConvertTimeout: 转换超时
  WriteTgtUriFailed: 写入失败
  ExportFileError: 处理文件内容失败，请检查源文档是否能够正常打开
  NeedPassword: 需要密码
```

## 响应 400

```javascript
// taskId 错误
{
    "name":"BadRequest",
    "message":"Invalid taskId!",
    "status":400
}
```

## 响应 404

```javascript
{
    "name":"NotFound",
    "message":"Document not found",
    "status":404
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