# 文档翻页

{% api-method method="put" host="https://shangzhibo.tv/api" path="/v2/activity/:id/doc/:docId" %}
{% api-method-summary %}
文档修改, 用于翻页
{% endapi-method-summary %}

{% api-method-description %}
如果需要修改观看页显示文档，可将 docId 替换为 **default**  
  
eg: http://shangzhibo.tv/api/v2/activity/:id/doc/default
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
活动 Id
{% endapi-method-parameter %}

{% api-method-parameter name="docId" type="integer" required=true %}
文档 Id, 若要修改默认文档，可将此参数改为 default
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}
默认是: application/json
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

{% endapi-method-response-example-description %}

```javascript
// 正常返回结果
{
  "result": true,
  "index": 5, // 文档页所在索引
  "page": "https://office.shangzhibo.tv/105131/6527135/1563368326939/9d4f6af0-a892-11e9-823f-4bd7ee2b7b5b-6.jpg" // 文档页链接
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
文档操作不合法
{% endapi-method-response-example-description %}

```javascript
// 文档未转码完成时
{
    "name":"BadRequest",
    "message":"当前文档正在转码或转码失败，暂时无法操作",
    "status":400
}

// 当前页数不能超过总页数
{
    "name":"BadRequest",
    "message":"当前页数不能超过总页数",
    "status":400
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
文档未找到
{% endapi-method-response-example-description %}

```javascript
{
    "name":"NotFound",
    "message":"Doc Not Found",
    "status":404
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=429 %}
{% api-method-response-example-description %}
接口频率限制为 10次 / 秒
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

