# 上传文档 V2

{% api-method method="post" host="https://shangzhibo.tv/api" path="/v2/activity/:id/doc" %}
{% api-method-summary %}
文档上传
{% endapi-method-summary %}

{% api-method-description %}
**支持的文档后缀： doc、docx、pdf、ppt、pptx  
一个接口一次只能上传一个文件  
频率限制为 1 次 / 秒**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
multipart/form-data
{% endapi-method-parameter %}

{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer:&lt;access token&gt;  
获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
返回 taskId 以便于查询文档转码进度
{% endapi-method-response-example-description %}

```javascript
{
    "taskId":"ef141163-2572-49fe-951a-1501cb7ce914"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=429 %}
{% api-method-response-example-description %}
接口频率限制为 1次 / 秒
{% endapi-method-response-example-description %}

```javascript
{
    "name":"TooManyRequests",
    "message":"请求速度太频繁了, 请于xxx后重试",
    "status":429
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## 文件上传示例代码:

```markup
<html>
    <form name="form" action="https://shangzhibo.tv/api/v2/activity/{id}/doc"  method="POST" enctype ="multipart/form-data">
    <input type="file" name="filename">
    <input type="submit" value="submit">
</form>
</html>
```

## 请求示例：

```bash
curl -H "Authorization: bearer xxxxx" "http://shangzhibo.tv/api/v2/activity/:id/doc" -F file=@raft.pdf
```

