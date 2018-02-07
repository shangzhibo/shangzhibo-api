# 上直播 API 简介

### API 介绍 {#api介绍}

#### 简介 {#简介}

上直播 API 提供基础的功能接口，满足您的二次开发需求。

上直播 API 需要使用 accessToken 发起 API 请求。

#### API 使用步骤 {#api使用步骤}

API 的使用分为三步：

1.成为旗舰版用户

2.得到 ACCESS TOKEN：请咨询我司商务，杨经理（18968187008）、彭经理（15167172618）。

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

