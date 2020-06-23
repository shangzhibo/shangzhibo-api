# 获取指定活动的回看视频列表

## 接口

获取媒体库回看视频列表

```javascript
GET /api/activity/{id}/playlist/playback
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
/api/activity/3180028/playlist/playback
```

## 响应参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| id | string | 视频列表 ID |
| activityId | string | 活动 ID |
| name | string | 视频列表名称 |
| updatedAt | string | 更新时间 |
| createdAt | string | 创建时间 |
| medias | array | 视频信息列表 |

## 响应示例

```javascript
{
    "id": 186655,
    "activityId": "3180028",
    "name": "录制回看",
    "createdAt": "2019-05-30T08:24:25.000Z",
    "updatedAt": "2019-05-30T08:24:26.000Z",
    "medias": [
        {
            "meta": {
                "duration": 180.557,
                "storage_bucket": "shangzhibo-aliyun",
                "storage_path": "/record/onelive/3180028-IeZ7BVH8wc/2019-05-30-16-18-23_2019-05-30-16-21-23.m3u8"
            },
            "isProcessThumbnail": false,
            "isProcessPlaylist": false,
            "id": 1522906,
            "activityId": "3180028",
            "path": "//recorder.shangzhibo.tv/record/onelive/3180028-IeZ7BVH8wc/2019-05-30-16-18-23_2019-05-30-16-21-23.m3u8",
            "source": "record",
            "thumbnailPath": "//aliyunimg.shangzhibo.tv/record/onelive/3180028-IeZ7BVH8wc/2019-05-30-16-18-23_2019-05-30-16-21-23.m3u8-preview.jpg",
            "playlistPath": "//recorder.shangzhibo.tv/record/onelive/3180028-IeZ7BVH8wc/2019-05-30-16-18-23_2019-05-30-16-21-23.m3u8",
            "taskId": null,
            "playbackTitle": null,
            "startedAt": "2019-05-30T08:18:22.000Z",
            "endedAt": "2019-05-30T08:21:24.000Z",
            "createdAt": "2019-05-30T08:24:25.000Z",
            "updatedAt": "2019-05-30T08:24:27.000Z"
        }
    ]
}
```

