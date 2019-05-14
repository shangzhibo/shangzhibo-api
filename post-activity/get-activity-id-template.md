# 获取指定活动模板

## 接口

获取模板

```javascript
GET /api/activity/{id}/template
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

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

### 响应样例

```javascript
{
    "data": {
        "imgLogo": "https://shangzhibo-img.b0.upaiyun.com/system/custom/shangzhibo/logo.svg",
        "imgCover": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507690130834/1507690130805_01.jpg",
        "imgMobileCover": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/default-mobile-index.png",
        "followImg": "https://shangzhibo-img.b0.upaiyun.com/system/activity/template/followImg.jpg",
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
        "isAdEnabled": false,
        "adList": [
            {
                "adContent": "广告栏文案",
                "adUrl": "http://shangzhibo.tv",
                "type": "text"
            }
        ],
        "isVoteFloatingEnabled": true,
        "isVoteBannerEnabled": false,
        "imgDescription": [
            {
                "title": "聊天室",
                "chatRoom": true
            },
            {
                "title": "活动简介",
                "url": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1511935321718/1511935321682_01.jpg"
            },
            {
                "title": "富文本菜",
                "richText": "<p>测试富文本内容</p>"
            }
        ],
        "auth": {
            "methods": [],
            "payPrompt": "欢迎观看直播",
            "payPrice": 1,
            "isTrailEnabled": false,
            "trailTimeout": 300,
            "payExpiredTimeout": 0,
            "isSinglePasscodeEnabled": false,
            "private": {
                "allowedMobileList": []
            }
        },
        "docs": [
            {
                "basePath": "https://shangzhibo-img.b0.upaiyun.com/client/activity/5966003/doc/1556100891653",
                "originalname": "经济法基础第二场.pdf",
                "filename": "b19d28b42d53052a880bc0f6b631e0dd.pdf",
                "pageCount": 118,
                "currentPage": 0
            }
        ],
        "currentDoc": {
            "basePath": "https://shangzhibo-img.b0.upaiyun.com/client/activity/5966003/doc/1556100891653",
            "originalname": "经济法基础第二场.pdf",
            "filename": "b19d28b42d53052a880bc0f6b631e0dd.pdf",
            "pageCount": 118,
            "currentPage": 42
        },
        "imgBackground": "https://shangzhibo-img.b0.upaiyun.com/client/user/100020/1507693918419/1507693918391_08.jpg",
        "isGiftEnabled": true,
        "isFollowEnabled": false,
        "colorBackground": "181818",
        "isResolutionEnabled": false,
        "resolutionTypes": [],
        "isSubscribeEnabled": false,
        "subscribeMessage": "",
        "subscribedMobileList": [],
        "isDocEnabled": false,
        "isDocFlatingEnabled": true,
        "isDocUnfoldEnabled": false,
        "isDocNotifyEnabled": false,
        "isDocTurningEnabled": true,
        "isGiftFloatingEnabled": true,
        "isGiftChatboxEnabled": false,
        "isGraphicEnabled": false,
        "isCountdownEnabled": false,
        "isFaqEnabled": false,
        "isFaqFloatingEnabled": true,
        "isFaqChatboxEnabled": false,
        "isVoteChatboxEnabled": false,
        "isVoteDisableClose": false,
        "isRegistrationEnabled": false,
        "registration": [],
        "isCandyEnabled": false,
        "isShareCardEnabled": true,
        "isCommentDisabled": false,
        "isLiveTranscodeEnabled": false,
        "isPageEnabled": false,
        "isLiveProtectionEnabled": false,
        "subAgentCount": 0
    },
    "updatedAt": "2019-04-18T03:04:56.000Z"
}
```

