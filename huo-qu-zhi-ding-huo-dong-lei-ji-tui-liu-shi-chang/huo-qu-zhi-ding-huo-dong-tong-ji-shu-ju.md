# 获取指定活动统计数据

## 接口

请求地址

```javascript
GET /api/activity/stats
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| activityId | string | 需要获取统计数据的活动 ID | 是 |
| stats | Array of string | 统计参数 | 否 |

## stats 统计参数

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| highestUv | object | 最大 uv 数 |
| puv | integer | 累计 pv 和 uv 数 |
| ip | integer | 累计 ip 数 |
| liveTime | integer | 直播流播放总时长（单位：秒） |
| totalTime | integer | 有用户访问的总时长（单位：分钟） |
| timeline | Array of object | 随时间变化的在线人用户数 |
| device | object | 观看设备统计 |
| gender | object | 观看性别统计 |
| referrer | object | 访问来源域名 |
| region | Array of object | 访问地域统计 |

## 请求样例

```text
/api/activity/stats?activityId=8448124&stats=puv&stats=ip&stats=timeline&stats=liveTime&stats=region&stats=highestUv
```

## 响应示例

```javascript
{
    "timeline":[

    ],
    "liveTime":8860,
    "region":[
        {
            "province":"浙江",
            "number":202
        }
    ],
    "referrer":{
        "other":{
            "null":140,
            "manage.shangzhibo.tv":4,
            "open.weixin.qq.com":7,
            "shangzhibo.tv":51
        }
    },
    "device":{
        "iOS":18,
        "Android":7,
        "PC":177,
        "other":0
    },
    "highestUv":{
        "highestUv":17,
        "highestUvAt":"2020-05-12T06:22:00.000Z",
        "highestUvCollectedAt":"2020-08-18T00:51:11.000Z"
    },
    "pv":2042,
    "uv":413,
    "totalTime":0
}
```

