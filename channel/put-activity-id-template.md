## 修改指定活动模板

### 接口

修改模板

```js
PUT /api/activity/{id}/template
```

### 授权

请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| imgCover | string | 直播封面图片 | 否 |
| imgLogo | string | 直播 Logo | 否 |
| imgBackground | string | 播放页背景图片 | 否 |

#### 请求样例

```js
{
  "data": {
    "imgCover": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507690130834/1507690130805_01.jpg",
    "imgBackground": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507693918419/1507693918391_08.jpg",
  }
}
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| data.colorBackground | string | 背景颜色 |
| data.imgLogo | string | LOGO 图片 |
| data.imgCover | string | 封面图片 |
| data.imgBackground | string | 背景图片 |
| updatedAt | string | 最后一次更新配置的时间 |

#### 响应样例

```js
{
  "data": {
    "colorBackground": "",
    "imgLogo": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-logo.svg",
    "imgCover": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507690130834/1507690130805_01.jpg",
    "imgBackground": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507693918419/1507693918391_08.jpg",
  },
  "updatedAt": "2017-10-11T03:52:04.000Z"
}
```



