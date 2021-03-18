# 获取指定活动表单收集数据

## 接口

获取观众表单收集数据列表

```text
GET /api/v2/activity/:id/checkin/data/json
```

## 授权

请求header

```text
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| page | integer | 页数（默认第一页） | 否 |
| pageSize | integer | 每页显示数量（默认 10） | 否 |

## 请求样例

```text
GET /api/v2/activity/<活动ID>/checkin/data/json
```

## 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| pager | object |  |
| pager.page | integer | 当前页 |
| pager.pageSize | integer | 每页返回数量 |
| pager.total | integer | 明细总量 |
| items | array&lt;object&gt; | 明细列表 |
| id | integer | 数据 id |
| userId | null 或 integer | 用户 Id，**匿名用户此处为空** |
| sid | null 或者 string | 匿名用户此处有值 |
| createdAt | string | 创建时间 |
| updatedAt | string | 更新时间 |
| data | array&lt;object&gt; |  |
| title | string | 表单收集 agent 规定收集字段的名称 |
| value | string | 表单收集 agent 规定收集字段,用户填写的对应的值 |

## 响应示例

```text
{
  "pager": {
    "total": 14,
    "page": 1,
    "pageSize": 10
  },

  "items": [
    {
      "data": [
        {
          "title": "姓名",
          "value": "初"
        },
        {
          "title": "手机号",
          "value": "17007xxxxxx"
        },
        {
          "title": "微信号",
          "value": "xxxxxx"
        }
        ],
        "id": 46,
        "activityId": "10xxxx",
        "userId": 120xxxx,
        "sid": null,
        "createdAt": "2020-05-15T11:07:19.000Z",
        "updatedAt": "2020-05-15T11:07:19.000Z"
    },
  ]
}
```

