# 新建推、拉流容器

## 接口

新建推、拉流容器

```javascript
POST /api/v3/activity/:id/stream-jobs
```

## 新建推流容器【推荐】

[快捷方式](https://app.gitbook.com/@shangzhibo/s/api/la-liu-zhuan-tui/create-new-push-stream-job)

## 新建拉流容器【推荐】

[快捷方式](https://app.gitbook.com/@shangzhibo/s/api/la-liu-zhuan-tui/create-new-pull-stream-job)

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| type | enum&lt;pull, push&gt; | pull 表示拉流容器，push 表示推流容器 | 否, 默认为 push |
| address | string | 转推、拉流地址，要注意推、拉流地址是否有效 | 是 |
| party | string | 当 type=push 时，必填 | 否 |

### 请求样例

```javascript
curl -X POST -H 'authorization: bearer <accessToken>' \ 
    shangzhibo.tv/api/v3/activity/8930091/stream-jobs  \ 
    -d type=pull \
    -d address=rtmp://push.shangzhibo.tv/onelive/test \
    -d party=shangzhibo
```

## 响应

| 参数 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| id | integer | 容器 id |
| activityId | string | 活动 id |
| type | enum&lt;pull, push&gt; | pull 表示拉流容器，push 表示推流容器 |
| status | enum&lt;active, passive&gt; | active 表示容器已经开启，passive 表示容器已经关闭 |
| createdAt | string | 创建时间 |
| updatedAt | string | 更新时间 |

## 响应样例

```javascript
{
  "id": 21524,
  "activityId": "349392",
  "type": "pull",
  "party": "",
  "address": "https://doc.shangzhibo.tv/client/user/105131/1587463656049/1587463656049.mp4",
  "status": "passive",
  "pid": 19209,
  "provider": "luffy",
  "createdAt": "2020-06-03T08:44:19.000Z",
  "updatedAt": "2020-06-03T08:54:15.000Z"
}
```

