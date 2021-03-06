# 获取活动视频列表

## 接口

获取视频列表列表

```text
GET /api/activity/:id/playlist/custom
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

```text
/api/activity/8448124/playlist/custom
```

## 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| id | integer | 播放列表 id |
| name | string | 播放列表名称 |
| activityId | string | 活动 id |
| medias | array | 视频信息列表 |
| mediaIds | array | 播放列表媒体 id |

## 响应示例

```javascript
{
    "mediaIds":[
        2907627
    ],
    "id":713324,
    "activityId":"10438142",
    "name":"视频列表",
    "createdAt":"2021-05-27T03:43:53.000Z",
    "updatedAt":"2021-06-18T08:59:23.881Z",
    "medias":[
        {
            "meta":{
                "storage_bucket":"shangzhibo-img",
                "storage_path":"/resources/120489/0/56aeda0423004f9xxxxxx4cf5.mp4",
                "duration":772.1426360000007,
                "size":0
            },
            "isCostStorage":true,
            "id":2907627,
            "agentId":120489,
            "activityId":"0",
            "path":"//doc.shangzhibo.tv/resources/120489/0/56aeda0423004f9xxxxx5.mp4",
            "source":"upload",
            "isProcessThumbnail":false,
            "thumbnailPath":"//doc.shangzhibo.tv/resources/120489/0/56aeda04230xd7134cf5-prexxxxview.jpg",
            "isProcessPlaylist":false,
            "playlistPath":"//doc.shangzhibo.tv/resources/120489/0/56aeda0423xxxxxx34cf5-processed.m3u8",
            "taskId":"457bbe5358cxxxxxx807e56ec",
            "playbackTitle":"2.JSX、createElement和虚拟DOM的关系",
            "startedAt":null,
            "endedAt":null,
            "createdAt":"2021-03-31T05:00:33.000Z",
            "updatedAt":"2021-06-17T18:00:13.000Z",
            "originalVideo":"//doc.shangzhibo.tv/resources/120489/0/56axxxxxxxxx7eb91fd7134cf5.mp4"
        },
        {
            "meta":{
                "storage_bucket":"shangzhibo-img",
                "storage_path":"/resources/120489/0/56aeda0423004f9xxxxxx4cf5.mp4",
                "duration":772.1426360000007,
                "size":0
            },
            "isCostStorage":true,
            "id":2907627,
            "agentId":120489,
            "activityId":"0",
            "path":"//doc.shangzhibo.tv/resources/120489/0/56aeda0423004f9xxxxx5.mp4",
            "source":"upload",
            "isProcessThumbnail":false,
            "thumbnailPath":"//doc.shangzhibo.tv/resources/120489/0/56aeda04230xd7134cf5-prexxxxview.jpg",
            "isProcessPlaylist":false,
            "playlistPath":"//doc.shangzhibo.tv/resources/120489/0/56aeda0423xxxxxx34cf5-processed.m3u8",
            "taskId":"457bbe5358cxxxxxx807e56ec",
            "playbackTitle":"2.JSX、createElement和虚拟DOM的关系",
            "startedAt":null,
            "endedAt":null,
            "createdAt":"2021-03-31T05:00:33.000Z",
            "updatedAt":"2021-06-17T18:00:13.000Z",
            "originalVideo":"//doc.shangzhibo.tv/resources/120489/0/56axxxxxxxxx7eb91fd7134cf5.mp4"
        }
    ]
}
```

