# 修改指定活动媒体库文件信息

## 接口

修改媒体库文件信息

```javascript
PUT /api/activity/{id}/media/bulk
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| id | integer | 视频ID |
| isPrologue（deprecated） | boolean | 是否是预设视频（已弃用） |
| prologueIndex（deprecated） | integer | 预设索引（已弃用） |
| isEpilogue（deprecated） | boolean | 是否是回看视频（已弃用） |
| epilogueIndex（deprecated） | integer | 回看索引（已弃用） |
| isPlayback（deprecated） | boolean | 是否是视频菜单视频（已弃用） |
| playbackIndex（deprecated） | integer | 视频菜单索引（已弃用） |
| playbackTitle | string | 视频菜单视频名称 |

### 请求样例

```javascript
[
  {
    "id": 100023,
    "isPrologue": true,//已弃用
    "prologueIndex": 0,//已弃用
    "isEpilogue": true,//已弃用
    "epilogueIndex": 0,//已弃用
    "isPlayback": true,//已弃用
    "playbackIndex": 0,//已弃用
    "playbackTitle": "stringValue"
  }
]
```

## 响应

### 响应样例

```javascript
{
  "result": true
}
```

