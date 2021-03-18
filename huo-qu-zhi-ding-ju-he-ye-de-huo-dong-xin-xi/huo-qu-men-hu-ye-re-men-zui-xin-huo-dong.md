# 获取门户页 热门/最新 活动

## 接口

请求地址

```text
GET api/page/:id/activities
```

## 授权

请求header

```text
Authorization: Bearer <accessToken>
Content-Type: application/json
```

> 注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">id</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x95E8;&#x6237;&#x9875;id</td>
    </tr>
    <tr>
      <td style="text-align:left">page</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">&#x5F53;&#x524D;&#x9875;</td>
    </tr>
    <tr>
      <td style="text-align:left">pageSize</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">&#x6BCF;&#x9875;&#x6761;&#x6570;</td>
    </tr>
    <tr>
      <td style="text-align:left">orderBy</td>
      <td style="text-align:left">enum</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>popular&#xFF1A; &#x70ED;&#x95E8;&#x6D3B;&#x52A8;</p>
        <p>latest &#xFF1A; &#x6700;&#x65B0;&#x6D3B;&#x52A8;&#xFF08;default&#xFF09;</p>
      </td>
    </tr>
  </tbody>
</table>

```text
GET /api/page/:id/activities?page=1&pageSize=10&orderBy=popular
```

## 响应参数

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | integer | 活动id |
| name | string | 活动名字 |
| status | string | 直播线路状态 |
| isPushing | boolean | 是否正在推流 |
| startedAt | string | 活动开始时间 |
| endedAt | string | 活动结束时间 |
| createdAt | string | 创建时间 |
| link | string | 活动观看页地址 |
| pv | integer | 活动观看人数 |
| template | object | 活动一些配置参数 |

## 响应示例

```text
{
    "pager":{
        "page":1,
        "pageSize":99,
        "total":10
    },
    "items":[
        {
            "id":"10269952",
            "name":"色白花青",
            "status":"disabled",
            "agentId":120489,
            "isPushing":false,
            "startedAt":"2021-02-24T11:10:00.000Z",
            "endedAt":"2021-03-05T09:40:15.000Z",
            "createdAt":"2021-01-26T10:14:42.000Z",
            "updatedAt":"2021-03-05T09:40:30.000Z",
            "link":"http://shangzhibo.tv/watch/10269952",
            "pv":3004,
            "template":{
                "imgLogo":"https://doc.shangzhibo.tv/system/custom/shangzhibo/logo.svg",
                "imgCover":"https://doc.shangzhibo.tv/client/user/121765/1587869188431/1587869188394_158786918839399.png",
                "imgMobileCover":"https://doc.shangzhibo.tv/system/activity/template/default-mobile-index.png",
                "followImg":"https://doc.shangzhibo.tv/system/activity/template/followImg.jpg",
                "share":{
                    "wechat":{
                        "text":"",
                        "image":"https://doc.shangzhibo.tv/system/activity/template/default-share-img.png"
                    },
                    "qq":{
                        "text":"",
                        "image":"https://doc.shangzhibo.tv/system/activity/template/default-share-img.png"
                    },
                    "weibo":{
                        "text":"",
                        "image":"https://doc.shangzhibo.tv/system/activity/template/default-share-img.png"
                    }
                },
                "isCRMSignupEnabled":false,
                "isNoRepeatDrawEnabled":false,
                "auth":{
                    "methods":[

                    ],
                    "payPrompt":"欢迎观看直播",
                    "payPrice":1,
                    "isTrailEnabled":false,
                    "trailTimeout":300,
                    "payExpiredTimeout":0,
                    "isSinglePasscodeEnabled":false
                },
                "isWechatShareDisabled":true,
                "isHideDraw":false,
                "isLikeEnabled":true,
                "isAutoLikesEnabled":false,
                "colorBackground":"",
                "imgBackground":"https://doc.shangzhibo.tv/resources/120489/10269952/b2a32e93e25d9fd9e6513a56a0d0d9aa.jpg",
                "positionLogo":"hide",
                "imgLogoScale":100,
                "imgLogoTransparency":100,
                "countdownPosition":"leftTop",
                "liveMode":"online",
                "followName":"官方公众号",
                "followDescription":"关注后可收到最新动态哦",
                "mobileLayout":"overlay",
                "mobileTitleType":"text",
                "isResolutionEnabled":false,
                "resolutionTypes":[

                ],
                "isSubscribeEnabled":false,
                "subscribeMessage":"",
                "isDocEnabled":false,
                "isDocFlatingEnabled":true,
                "isDocUnfoldEnabled":false,
                "isDocNotifyEnabled":false,
                "isDocTurningEnabled":true,
                "isGiftEnabled":true,
                "isGiftFloatingEnabled":true,
                "isGiftChatboxEnabled":false,
                "isGraphicEnabled":false,
                "isCountdownEnabled":false,
                "isAdEnabled":false,
                "isFaqEnabled":false,
                "isFaqFloatingEnabled":true,
                "isFaqChatboxEnabled":false,
                "isVoteFloatingEnabled":true,
                "isVoteBannerEnabled":true,
                "isVoteChatboxEnabled":false,
                "isVoteDisableClose":false,
                "isShareCardEnabled":true,
                "isLiveTranscodeEnabled":false,
                "isPageEnabled":false,
                "isLiveProtectionEnabled":false,
                "promotions":[

                ],
                "checkinScene":"before",
                "isCommentDisabled":false,
                "wechatLoginPattern":"normal",
                "transcribeGuardConf":{
                    "fontSize":18,
                    "fontColor":"#FFF",
                    "opacity":90,
                    "showType":"level",
                    "text":"${username}"
                },
                "commentStyleCustomized":{
                    "template":0,
                    "tabsColor":"FFFFFF",
                    "backgroundImg":"",
                    "inputColor":"FFFFFF",
                    "fontColor":"000000",
                    "backgroundColor":"EEEEEE"
                },
                "commentAllowed":[
                    "agent",
                    "subagent"
                ]
            }
        }
    ]
}
```



