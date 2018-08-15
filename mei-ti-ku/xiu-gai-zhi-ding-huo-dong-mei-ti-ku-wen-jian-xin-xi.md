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
| path | string | 文件路径 |
| isPrologue | boolean | 是否是预设视频 |
| prologueIndex | integer | 预设索引 |
| isEpilogue | boolean | 是否是回看视频 |
| epilogueIndex | integer | 回看索引 |
| isPlayback | boolean | 是否是视频菜单视频 |
| playbackIndex | integer | 视频菜单索引 |
| playbackTitle | string | 视频菜单视频名称 |

#### 请求样例

```js
[
  {
    "path": "http://shangzhibo-aliyun.b0.upaiyun.com/record/2018-07-18/live/1/2018-07-18-12-12-23_2018-07-18-12-55-05.m3u8",
    "isPrologue": true,
    "prologueIndex": 0,
    "isEpilogue": true,
    "epilogueIndex": 0,
    "isPlayback": true,
    "playbackIndex": 0,
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



