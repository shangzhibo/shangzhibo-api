---
description: 该接口已经废弃
---

# 客户网站授权登录\(已废弃\)

客户网站授权登录可以在终端观众登录上直播活动页时，指定使用客户自己的用户系统进行登录，并将用户数据回传给上直播作用于数据统计、聊天头像昵称展示、付费判断依据等功能场景。

注意：该接口需要进行第三方登录定制服务后才可以使用，具体请联系所属商务经理。

## 业务流程图

### 场景一

未登录用户通过客户网站进入直播

![](../.gitbook/assets/jietu20180910-170915%20%283%29.png)

### 场景二

未登录用户通过上直播页面进入直播

![](../.gitbook/assets/jietu20180910-170926%20%282%29%20%284%29%20%284%29.png)

## 接口

回传用户数据

```javascript
POST /api/callback/user
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

以下参数需要在 body 中提供

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| strUid | string | 唯一标识用户的 ID | 是 |
| cookieId | string | 为每个访客在 cookie 中生成的唯一标识（par.shangzhibo.sid） | 是 |
| nickname | string | 用户昵称（评论时显示） | 是 |
| avatar | string | 用户头像（评论时显示），必须使用 https:// | 是 |
| sex | string | 用户性别 | 是 |
| country | string | 国家 | 否 |
| province | string | 省份 | 否 |
| city | string | 城市 | 否 |

### 特殊情况说明

APP 环境或者未定制上直播播放域名的客户可能无法使用 cookie（par.shangzhibo.sid） 方式，此时可以将访客唯一标识通过播放页 URL 后加参数带过来。

`http://shangzhibo.tv/watch/{activityId}?parSid=xxxxx`

并将 parSid 仍通过本接口 cookieId 字段传给上直播。

如果参数里面含有特殊字符（如：`+` 、`/` 等在 URL具有含义的字符） 需要对参数进行 URI encode。

```javascript
let parSid = 'rcTDGfQv7p8P+g//DZ0wFQ=='
parSid = encodeURIComponent(parSid)
// parSid === 'rcTDGfQv7p8P%2Bg%2F%2FDZ0wFQ%3D%3D'
```

### 请求样例

```javascript
{
  "strUid": 2580821,
  "cookieId": "TkSA4HjIjuFQPyFSoB_0ULx821k4b1Fq",
  "nickname": "兰海ena",
  "avatar": "https://static.itdks.com/files/default/2017/09-28/17403642672f970434.jpg",
  "sex": "male",
  "country": "China",
  "province": "Zhejiang",
  "city": "Hangzhou"
}
```

## 响应

### 响应样例

```javascript
{
  "result": true,
}
```

