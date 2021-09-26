# 创建合辑

## 接口

创建合辑

```javascript
POST /api/v3/catalog
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 `accessToken` ，请咨询杨经理（18968187008）。

## 参数

| 参数 | 参数类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| name | string | 是 | 合辑名称, 长度 1 ~ 45 |

### 请求示例

```bash
curl -H "Content-Type: application/json" \
  -H "Authorization: Bearer <accessToken>"  \
  -X "POST" http://shangzhibo.tv/api/v3/catalog -d $'{"name": "测试"}'
```

## 响应 200

| 参数 | 参数类型 | 描述 |
| :--- | :--- | :--- |
| id | integer | 合辑唯一 ID |
| name | string | 合辑名称, 长度 1 ~ 45 |
| agentId | integer | 合辑归属者账号 ID |
| link | string | 合辑打开链接 |
| chapters | array | 合辑内容 |
| chapters\[N\].selection | string | 章节名称, 默认为空字符串 |
| chapters\[N\].activityIds | array | 活动 ID 列表 |
| chapters\[N\].activities | array | 活动列表对应的活动内容 |
| chapters\[N\].activities\[M\].id | string | 活动ID |
| chapters\[N\].activities\[M\].name | string | 活动名称 |
| chapters\[N\].activities\[M\].link | string | 活动打开链接 |
| chapters\[N\].activities\[M\].type | enum\["video", "live"\] | 活动类型， video 表示视频，live 表示直播 |
| createdAt | string | 创建时间 |
| updatedAt | string | 最后更新时间 |

### 响应样例

```javascript
{
  "id": 1,
  "name": "测试",
  "agentId": 105131,
  "chapters": [{
    "selection": "",
    "activityIds": [],
    "activities": []
  }],
  "createdAt": "2021-08-30T01:54:34.917Z",
  "updatedAt": "2021-08-30T01:54:34.917Z"
}
```

## 响应 400

### 合辑名称已经存在

```javascript
{
  "status": 400,
  "name": "BadRequest",
  "message": "Catalog name already existed",
}
```

