## 修改指定活动媒体库文件信息

### 接口

修改媒体库文件信息

```js
PUT /api/activity/{id}/media/bulk
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| id | integer | 视频ID |
| isPrologue（deprecated） | boolean | 是否是预设视频（即将弃用） |
| prologueIndex（deprecated） | integer | 预设索引（即将弃用） |
| isEpilogue（deprecated） | boolean | 是否是回看视频（即将弃用） |
| epilogueIndex（deprecated） | integer | 回看索引（即将弃用） |
| isPlayback（deprecated） | boolean | 是否是视频菜单视频（即将弃用） |
| playbackIndex（deprecated） | integer | 视频菜单索引（即将弃用） |
| playbackTitle | string | 视频菜单视频名称 |

#### 请求样例

```js
[
  {
    "id": 100023,
    "isPrologue": true,//即将弃用
    "prologueIndex": 0,//即将弃用
    "isEpilogue": true,//即将弃用
    "epilogueIndex": 0,//即将弃用
    "isPlayback": true,//即将弃用
    "playbackIndex": 0,//即将弃用
    "playbackTitle": "stringValue"
  }
]
```

### 响应

#### 响应样例

```js
{
  "result": true
}
```



