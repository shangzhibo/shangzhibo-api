# 文档查询

{% api-method method="get" host="https://shangzhibo.tv/api" path="/v2/activity/:id/doc/:docId" %}
{% api-method-summary %}
Get Doc
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
 活动 Id
{% endapi-method-parameter %}
{% api-method-parameter name="docId" type="integer" required=true %}
 文档 Id
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}
 默认是: application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
{% endapi-method-response-example-description %}

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

### 如果文档不存在, 则响应为空对象
```javascript 1.8
{}
```
{% endapi-method-response-example %}
