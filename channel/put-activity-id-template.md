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
| positionLogo | string | LOGO 布局（隐藏：hide；居左：topLeft；居右：topRight） | 否 |
| imgLogoScale | integer | LOGO 缩放百分比 \[1-100\] 整数 | 否 |
| imgLogoTransparency | integer | LOGO 透明度 \[1-100\] 整数 | 否 |
| imgBackground | string | 播放页背景图片 | 否 |
| isGiftEnabled | boolean | 互动打赏功能开关 | 否 |
| imgDescription | array | 自定义菜单（数组元素定义见下面的 title 和 url） | 否 |
| title | string | 菜单标签 | 否 |
| url | string | 图片链接 | 否 |
| share.qq.image | string | QQ 分享 logo | 否 |
| share.qq.text | string | QQ 分享文字 | 否 |
| share.wechat.image | string | 微信分享 logo | 否 |
| share.wechat.text | string | 微信分享文字 | 否 |
| share.weibo.image | string | 微博分享 logo | 否 |
| share.weibo.text | string | 微博分享文字 | 否 |

#### 请求样例

```js
{
  "data": {
    "imgCover": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507690130834/1507690130805_01.jpg",
    "imgBackground": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507693918419/1507693918391_08.jpg",
    "isGiftEnabled": true,
    "imgDescription": [
      {
        "title": "活动简介",
        "url": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1511935321718/1511935321682_01.jpg"
      } 
    ]
    "share": {
      "qq": {
        "image": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-share-img.png",
        "text": "QQ 分享测试"
      },
      "wechat": {
        "image": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-share-img.png",
        "text": "微信分享测试"
      },
      "weibo": {
        "image": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-share-img.png",
        "text": "微博分享测试"
      }
    }
  }
}
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| data.colorBackground | string | 背景颜色 |
| data.imgLogo | string | LOGO 图片 |
| data.positionLogo | string | LOGO 布局 |
| data.imgCover | string | 封面图片 |
| data.imgBackground | string | 背景图片 |
| data.imgMobileCover | string | 直播内容介绍图片，点击进入直播 |
| data.imgDescription | array | 自定义菜单 |
| data.share.wechat | object | 微信分享设置，包括分享截图和文本 |
| data.share.qq | object | QQ分享设置，包括分享截图和文本 |
| data.share.weibo | object | 微博分享设置，包括分享截图和文本 |
| data.isResolutionEnabled | boolean | 是否启用清晰度设置 |
| data.resolutionTypes | array | 清晰度类型，允许多选 |
| data.isSubscribeEnabled | boolean | 是否启用开播提醒 |
| data.subscribeMessage | string | 开播提醒内容 |
| data.subscribedMobileList | array | 订阅开播提醒的手机列表 |
| data.isFollowEnabled | boolean | 是否启用公众号关注 |
| data.followImg | string | 公众号关注二维码 |
| data.isDocEnabled | boolean | 是否启用文档直播 |
| data.isDocNotifyEnabled | boolean | 是否开启文档提醒 |
| data.docs | array | 文档信息 |
| data.isGiftEnabled | boolean | 是否启用礼物打赏功能 |
| data.isGraphicEnabled | boolean | 是否启用图文直播 |
| data.isCountdownEnabled | boolean | 是否启用倒计时 |
| data.auth.methods | array | 授权方式 |
| data.auth.payPrompt | string | 提示文字 |
| data.auth.payPrice | number | 观看价格 |
| data.auth.isTrailEnabled | boolean | 付费观看是否允许试看 |
| data.auth.trailTimeout | integer | 试看时间，单位（秒） |
| data.auth.private | object | 仅供服务端使用，不在观看页出现的配置 |
| data.isVoteEnabled | boolean | 是否启用投票功能 |
| data.isAdEnabled | boolean | 是否启用广告栏 |
| updatedAt | string | 最后一次更新配置的时间 |

#### 响应样例

```js
{
  "data": {
    "colorBackground": "",
    "imgLogo": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-logo.svg",
    "imgCover": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507690130834/1507690130805_01.jpg",
    "imgMobileCover": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-mobile-index.png",
    "imgDescription": [
      {
        "title": "活动简介",
        "url": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1511935321718/1511935321682_01.jpg"
      }
    ]
    "share": {
      "qq": {
        "image": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-share-img.png",
        "text": "QQ 分享测试"
      },
      "wechat": {
        "image": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-share-img.png",
        "text": "微信分享测试"
      },
      "weibo": {
        "image": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-share-img.png",
        "text": "微博分享测试"
      }
    },
    "imgBackground": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507693918419/1507693918391_08.jpg",
    "positionLogo": "topLeft",
    "isResolutionEnabled": false,
    "resolutionTypes": [],
    "isSubscribeEnabled": false,
    "subscribeMessage": "",
    "subscribedMobileList": [],
    "isFollowEnabled": true,
    "followImg": "",
    "docs": [],
    "isDocEnabled": false,
    "isDocNotifyEnabled": false,
    "isGiftEnabled": true,
    "isGraphicEnabled": false,
    "isCountdownEnabled": false,
    "auth": {
      "methods": [],
      "payPrompt": "欢迎观看直播",
      "payPrice": 1,
      "isTrailEnabled": false,
      "trailTimeout": 300,
      "private": {}
    },
    "isVoteEnabled": false,
    "isAdEnabled": true
  },
  "updatedAt": "2017-10-11T03:52:04.000Z"
}
```



