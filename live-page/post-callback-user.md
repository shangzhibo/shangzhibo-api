## 客户网站授权登录

客户网站授权登录可以在终端观众登录上直播活动页时，指定使用客户自己的用户系统进行登录，并将用户数据回传给上直播作用于数据统计、聊天头像昵称展示、付费判断依据等功能场景。

### 业务流程图

#### 场景一
未登录用户通过客户网站进入直播

<img src="http://shangzhibo-img.b0.upaiyun.com/test/Scenes1.png" alt="场景一" width="500" height="411">

#### 场景二
未登录用户通过上直播页面进入直播

<img src="http://shangzhibo-img.b0.upaiyun.com/test/Scenes2.png" alt="场景一" width="500" height="411">

### 接口
回传用户数据

```js
POST /api/callback/user
```
### 授权
请求 header

```
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

### 参数

| 参数       | 参数类型    | 参数说明       | 是否必填 |
| -------- | ------- | ---------- | ---- |
| identity | string  | 客户标识（公司简写）       | 是    |
| uid      | integer | 唯一标识用户的 ID（数字类型） | uid 与 strUid 二选一   |
|strUid | string | 唯一标识用户的 ID（字符串类型）| uid 与 strUid 二选一 |
| cookieId      | string  | cookieId（为每个访客在 cookie 中生成的唯一标识） | 是    |
| nickname | string  | 用户昵称(评论时显示)     | 是    |
| avatar   | string  | 用户头像(评论时显示)     | 是    |
| sex      | string  | 用户性别       | 是    |
| country  | string  | 国家         | 否    |
| province | string  | 省份         | 否    |
| city     | string  | 城市         | 否    |

#### 请求样例

```js
{
  "identity": "huaban",
  "uid": 2580821,
  "cookieId": "TkSA4HjIjuFQPyFSoB_0ULx821k4b1Fq",
  "nickname": "兰海ena",
  "avatar": "http://static.itdks.com/files/default/2017/09-28/17403642672f970434.jpg",
  "sex": "male",
  "country": "China",
  "province": "Zhejiang",
  "city": "Hangzhou"
}
```

### 响应

#### 响应样例
```js
{
  "result": true,
}
```


