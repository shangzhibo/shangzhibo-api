# 修改活动视频列表

## 接口

修改活动视频列表

```javascript
PUT /api/activity/{id}/playlist/{playlistId}
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

```javascript
/api/activity/3180028/playlist/186655

[1523064,1523063,1523057]
```

## 请求参数

| 类型 | 描述 |
| :--- | :--- |
| array | 直接将视频 ID 写在 body 中，\[mediaid1,mediaid2,mediaid3\] |

## 响应示例

```javascript
{
    "result": true
}
```

