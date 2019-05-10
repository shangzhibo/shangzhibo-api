# 获取指定活动统计数据

## 接口

请求地址

```javascript
GET /api/activity/stats
```

## 授权

请求 header

```text
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| activityId | string | 需要获取统计数据的活动 ID | 是 |
| stats | Array of string | 统计参数 | 否 |

## stats 统计参数

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
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
/api/activity/stats?activityId=8448124&stats=puv&stats=ip&stats=timeline&stats=liveTime&stats=region
```

## 响应示例

```text
{
  "pv": 34,
  "uv": 20,
  "ip": 20,
  "liveTime": 5,
  "totalTime": 300,
  "timeline": [
    {
      "time": "Wed Nov 16 2016 11:52:15 GMT+0800 (CST)",
      "count": 23
    }
  ],
  "device": {
    "iOS": 999,
    "Android": 888,
    "PC": 777,
    "other": 666
  },
  "gender": {
    "male": 99,
    "female": 88,
    "unknown": 77
  },
  "referrer": {
    "wechat": 999,
    "shangzhibo": 888,
    "other": {
      "live.huaban.com": 666
    }
  },
  "region": [
    {
      "province": "浙江",
      "number": 100
    },
    {
      "province": "安徽",
      "number": 200
    },
    {
      "province": "河南",
      "number": 200
    },
    {
      "province": "山东",
      "number": 200
    },
    {
      "province": "河北",
      "number": 200
    }
  ]
}
```

