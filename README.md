# 上直播 API 简介

### API 介绍 {#api介绍}

#### 简介 {#简介}

上直播 API 提供基础的功能接口，满足您的二次开发需求。

上直播 API 需要使用 accessToken 发起 API 请求。

#### 主要功能 {#简介}

| 功能名称 | 详细内容 |
| :--- | :--- |
| 活动 API | 支持对活动进行增、删、改、查，支持发起、结束直播，支持活动相关数据查询 |
| 评论 API | 支持获取活动历史聊天（评论）记录，添加聊天（评论） |
| 媒体库 API | 支持获取媒体库中上传视频以及回看视频列表，从而获取视频播放地址 |
| 观众账号 API | 用于实现通过客户用户信息登录上直播进行观看及付费，使两边用户数据同步 |
| 播放页 API | 支持获取指定活动的 iframe 嵌入代码，并支持通过嵌入代码提供直播信息的上报 |

#### API 接入步骤 {#api使用步骤}

![](/assets/QQ20180207-165606.png)

API 的接入分为三步：

1.成为旗舰版用户：[前往官网升级](http://shangzhibo.tv/price)

2.得到 accessToken：请咨询我司商务，杨经理（18968187008）、彭经理（15167172618）。

3.使用第二步中得到的 accessToken，便可以访问上直播 API 中的全部接口服务

需要在请求 header 中添加以下请求头信息：

```
Authorization: Bearer <accessToken>

Content-Type: application/json
```

如果请求头没有带上 accessToken，上直播 API 的安全机制将会视其为未授权访问操作，并将其拦截。

#### API 域名 {#api域名}

`http://shangzhibo.tv`

support https

