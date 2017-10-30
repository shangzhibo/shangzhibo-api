## 修改频道

### 接口
修改频道

```js
PUT /api/activity/{id}
```
### 授权
请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数        | 参数类型     | 参数说明   | 是否必填 |
| --------- | -------- | ------ | ---- |
| name      | string   | 频道名称   | 否    |
| startedAt | datetime | 直播开始时间 | 否    |
| endedAt   | datetime | 直播结束时间 | 否    |

#### 请求样例

```js
{
  "name": "哈哈哈",
  "start_time": "2017-08-09 12:00:00",
  "end_time": "2017-08-10 13:00:00"
}
```

### 响应

#### 响应样例
```js
{
  "result": true
}
```


