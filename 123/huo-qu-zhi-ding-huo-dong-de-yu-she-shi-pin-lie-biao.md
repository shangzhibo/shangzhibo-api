# 获取指定活动的预设视频列表

## 接口

获取媒体库预设视频列表

```javascript
GET /api/activity/{id}/playlist/preset
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

无

## 请求样例

```javascript
/api/activity/3180028/playlist/preset
```

## 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| mediaIds | array | 视频 ID |
| id | string | 视频列表 ID |
| activityId | string | 活动 ID |
| name | string | 视频列表名称 |
| updatedAt | string | 更新时间 |
| createdAt | string | 创建时间 |

## 响应示例

```javascript
{
    "mediaIds": [
        1523064,
        1523063,
        1523057
    ],
    "id": 186654,
    "activityId": "3180028",
    "name": "预设视频",
    "updatedAt": "2019-06-05T02:10:05.004Z",
    "createdAt": "2019-05-30T08:24:25.000Z",
    "medias": [
        {
            "meta": {
                "storage_bucket": "shangzhibo-img",
                "storage_path": "/client/user/100001/1559209011381/1559209011443_3.mp4",
                "duration": 24.999999,
                "size": 4901675
            },
            "isProcessThumbnail": false,
            "isProcessPlaylist": false,
            "id": 1523064,
            "activityId": "3180028",
            "path": "//doc.shangzhibo.tv/client/user/100001/1559209011381/1559209011443_3.mp4",
            "source": "upload",
            "thumbnailPath": "//doc.shangzhibo.tv/client/user/100001/1559209011381/1559209011443_3-preview.jpg",
            "playlistPath": "//doc.shangzhibo.tv/client/user/100001/1559209011381/1559209011443_3-processed.m3u8",
            "taskId": "f01fbe6956174d299be77eea58769a94",
            "playbackTitle": null,
            "startedAt": null,
            "endedAt": null,
            "updatedAt": "2019-06-03T08:58:02.000Z",
            "createdAt": "2019-05-30T09:36:52.000Z"
        },
        {
            "meta": {
                "storage_bucket": "shangzhibo-img",
                "storage_path": "/client/user/100001/1559209006391/1559209006444_1.mp4",
                "duration": 7.3,
                "size": 4091272
            },
            "isProcessThumbnail": false,
            "isProcessPlaylist": false,
            "id": 1523063,
            "activityId": "3180028",
            "path": "//doc.shangzhibo.tv/client/user/100001/1559209006391/1559209006444_1.mp4",
            "source": "upload",
            "thumbnailPath": "//doc.shangzhibo.tv/client/user/100001/1559209006391/1559209006444_1-preview.jpg",
            "playlistPath": "//doc.shangzhibo.tv/client/user/100001/1559209006391/1559209006444_1-processed.m3u8",
            "taskId": "6d5bce7b32c24af2a2ea20fce275d520",
            "playbackTitle": null,
            "startedAt": null,
            "endedAt": null,
            "updatedAt": "2019-06-03T08:58:02.000Z",
            "createdAt": "2019-05-30T09:36:47.000Z"
        },
        {
            "meta": {
                "storage_bucket": "shangzhibo-img",
                "storage_path": "/client/user/100001/1559208881035/1559208881085_3.mp4",
                "duration": 24.999999,
                "size": 4901675
            },
            "isProcessThumbnail": false,
            "isProcessPlaylist": false,
            "id": 1523057,
            "activityId": "3180028",
            "path": "//doc.shangzhibo.tv/client/user/100001/1559208881035/1559208881085_3.mp4",
            "source": "upload",
            "thumbnailPath": "//doc.shangzhibo.tv/client/user/100001/1559208881035/1559208881085_3-preview.jpg",
            "playlistPath": "//doc.shangzhibo.tv/client/user/100001/1559208881035/1559208881085_3-processed.m3u8",
            "taskId": "b5742f66bb99483489ed83b90c977fc9",
            "playbackTitle": null,
            "startedAt": null,
            "endedAt": null,
            "updatedAt": "2019-06-03T08:58:02.000Z",
            "createdAt": "2019-05-30T09:34:42.000Z"
        }
    ]
}
```

