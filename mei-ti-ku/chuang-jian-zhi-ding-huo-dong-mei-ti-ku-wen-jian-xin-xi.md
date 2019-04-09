## 创建指定活动媒体库文件信息

### 接口

创建媒体库文件信息

```js
POST /api/activity/{id}/media
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
| id | string | 视频 ID |
| activityId | string | 活动 ID |
| path | string | 文件路径 |
| source | string | 视频类型（record 表示录制文件，upload 表示上传文件） |
| isPrologue（deprecated） | boolean | 是否是预设视频（即将弃用） |
| prologueIndex（deprecated） | integer | 预设索引（即将弃用） |
| isEpilogue（deprecated） | boolean | 是否是回看视频（即将弃用） |
| epilogueIndex（deprecated） | integer | 回看索引（即将弃用） |
| isProcessThumbnail | boolean | 是否在生成视频截图 |
| thumbnailPath | string | 视频截图地址 |
| isProcessPlaylist | boolean | 是否在生成 Playlist 文件 |
| playlistPath | string | Playlist 文件路径 |
| isPlayback（deprecated） | boolean | 是否是视频菜单视频（即将弃用） |
| playbackIndex（deprecated） | integer | 视频菜单索引（即将弃用） |
| playbackTitle | string | 视频菜单视频名称 |
| startedAt | string | 视频录制起始时间 |
| endedAt | string | 视频录制中止时间 |
| createdAt | string | 视频上传/录制生成时间 |
| updatedAt | string | 视频更新时间 |

#### 请求样例

```js
{
    "id": 150230,
    "activityId": "8448124",
    "path": "http://shangzhibo-aliyun.b0.upaiyun.com/record/2018-07-18/live/1/2018-07-18-12-12-23_2018-07-18-12-55-05.m3u8",
    "source": "upload",
    "isPrologue": false,//即将弃用
    "isEpilogue": true,//即将弃用
    "isProcessThumbnail": false,
    "isProcessPlaylist": false,
    "isPlayback": false,//即将弃用
    "prologueIndex": 0,//即将弃用
    "epilogueIndex": 0,//即将弃用
    "thumbnailPath": "http://shangzhibo-aliyunimg.b0.upaiyun.com/record/2018-07-18/live/1/2018-07-18-12-12-23_2018-07-18-12-55-05.m3u8-preview.jpg",
    "playlistPath": "http://shangzhibo-aliyun.b0.upaiyun.com/record/2018-07-18/live/1/2018-07-18-12-12-23_2018-07-18-12-55-05.m3u8",
    "taskId": null,
    "playbackIndex": null,//即将弃用
    "playbackTitle": null,
    "startedAt": "2018-07-18T04:12:24.000Z",
    "endedAt": "2018-07-18T04:55:06.000Z",
    "createdAt": "2018-07-18T04:58:07.000Z",
    "updatedAt": "2018-07-18T04:58:07.000Z"
}
```

### 响应

#### 响应样例

```js
{
  "result": true
}
```



