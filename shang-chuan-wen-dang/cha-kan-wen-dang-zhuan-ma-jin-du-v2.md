# 查看文档转码状态 V2

{% api-method method="get" host="https://shangzhibo.tv/api" path="/v2/activity/:id/doc" %}
{% api-method-summary %}
获取文档转码状态
{% endapi-method-summary %}

{% api-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="taskId" type="string" required=true %}
任务 ID  
如何获取
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer:&lt;access token&gt;  
获取 access token，请咨询杨经理（18968187008）、彭经理（15167172618）
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
// taskId 错误
{
    "name":"BadRequest",
    "message":"Invalid taskId!",
    "status":400
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
文件不存在
{% endapi-method-response-example-description %}

```javascript
{
    "name":"NotFound",
    "message":"Document not found",
    "status":404
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=429 %}
{% api-method-response-example-description %}
接口频率限制为 10 次 / 秒
{% endapi-method-response-example-description %}

```javascript
{
    "name":"TooManyRequests",
    "message":"请求速度太频繁了, 请于xxx后重试",
    "status":429
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "name":"InternalServerError",
    "message":"发生未知错误，请稍后重试",
    "status":500
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## 请求示例:

```bash
curl -H "Authorization: bearer xxx" "https://shangzhibo.tv/api/v2/activity/:id/doc?taskId=ef141163-2572-49fe-951a-1501cb7ce914"
```

