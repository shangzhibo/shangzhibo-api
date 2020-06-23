# 获取指定活动模板

## 接口

获取模板

```javascript
GET /api/activity/:id/template
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

无

### 请求样例

```javascript
/api/activity/8728620/template
```

## 响应

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| data.colorBackground | string | 背景颜色 |
| data.imgLogo | string | LOGO 图片 |
| data.positionLogo | string | LOGO 布局 |
| data.imgCover | string | 封面图片 |
| data.imgBackground | string | 背景图片 |
| data.imgMobileCover | string | 直播内容介绍图片，点击进入直播 |
| updatedAt | string | 最后一次更新配置的时间 |

### 响应样例

```javascript
{
    "data": {
        "imgLogo": "https://shangzhibo-img.b0.upaiyun.com/system/custom/shangzhibo/logo.svg",
        "imgCover": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507690130834/1507690130805_01.jpg",
        "imgMobileCover": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-mobile-index.png",
        "followImg": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/followImg.jpg"
        "imgBackground": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507693918419/1507693918391_08.jpg",
    },
    "updatedAt": "2019-04-18T03:04:56.000Z"
}
```

