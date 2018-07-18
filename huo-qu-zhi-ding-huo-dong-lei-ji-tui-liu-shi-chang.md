## 获取指定活动累计推流时长

### 接口

获取累计推流时长

```js
GET /api/activity/history
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| --- | --- | --- | --- |
| activityId | string | 需要获取推流时长的活动 ID | 是 |

### 请求样例

```
/api/activity/history?activityId=8448124
```

### 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| total | integer | 累计推流时长（单位：秒） |

### 响应示例

```
{
  "total": 42
}
```



