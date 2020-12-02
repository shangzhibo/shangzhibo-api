# 获取活动实时信息

## 接口

获取活动实时信息, 该接口限频 5次 / 分钟

```javascript
GET /api/v3/activity/:id/state
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

无

## 请求样例

```bash
curl -H 'authorization: bearer <accessToken>' \
	https://shangzhibo.tv/api/v3/activity/:id/state
```

## 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| concurrent | integer | 实时并发人数 |

## 响应示例

```javascript
{
  "concurrent": 100
}
```

