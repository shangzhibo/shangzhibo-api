## 获取活动列表

### 接口

获取活动列表

```
GET/activity
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数 | 参数类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| status | string | 是 | 活动状态，分别为“可用”（enabled）、“已结束”（disabled）、“已禁用”（forbidden） 和”已归档“（deleted） |

### 请求样例

```
/activity?status=enabled
```

### 响应参数

| 参数 | 类型 | 是否必填 | 描述 | 示例 |
| :--- | :--- | :--- | :--- | :--- |
| page | string | 是 | 一页显示几条 | 2 |
| pageSize | string | 是 | 页码 | 10 |
| total | string | 是 | 总条数 | 100 |
| id | string | 是 | 活动 ID | 8050309 |
| name | string | 是 | 活动名称 | 分享禁用测试活动 |
| status | string | 是 | 活动状态 | enabled |

### 响应示例

```
{
  "pager": {
    "page": 2,
    "pageSize": 10,
    "total": 100
  },
  "items": [
    {
      "id": "8050309",
      "name": "分享禁用测试活动",
      "status": "enabled",
      }
  ]
}
```

  


