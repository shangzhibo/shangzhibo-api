# 获取活动列表

## 接口

请求地址

```javascript
GET api/activity
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

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
      <td style="text-align:left">isArchived</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">&#x201C;true&#x201C; &#x8868;&#x793A;&#x5DF2;&#x5F52;&#x6863;&#xFF0C;&#x201C;false&#x201D;
        &#x8868;&#x793A;&#x672A;&#x5F52;&#x6863;</td>
    </tr>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">&#x6D3B;&#x52A8;&#x540D;&#x79F0;</td>
    </tr>
    <tr>
      <td style="text-align:left">isPushing</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">&#x662F;&#x5426;&#x5904;&#x4E8E;&#x63A8;&#x6D41;&#x72B6;&#x6001;</td>
    </tr>
    <tr>
      <td style="text-align:left">orderBy</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>&#x652F;&#x6301;&#x6392;&#x5E8F;&#x7684;&#x5B57;&#x6BB5;&#xFF1A;`createdAt`,
          `endedAt` , `startedAt` &#xFF1B;</p>
        <p>&#x53EF;&#x6309;&#x6B63;&#x5E8F;&#xFF08;ASC&#xFF09;&#x6216;&#x8005;&#x5012;&#x5E8F;&#xFF08;DESC&#xFF09;&#x6765;&#x6392;&#xFF0C;</p>
        <p>&#x6BD4;&#x5982;&#xFF1A;`createdAt DESC` &#x8868;&#x793A;&#x6309;&#x7167;&#x521B;&#x5EFA;&#x65F6;&#x95F4;&#x5012;&#x5E8F;&#x6392;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">page</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">&#x9875;&#x7801;</td>
    </tr>
    <tr>
      <td style="text-align:left">pageSize</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">&#x6BCF;&#x9875;&#x51E0;&#x6761;</td>
    </tr>
  </tbody>
</table>## 请求样例

```javascript
/api/activity?isArchived=false&page=42&pageSize=42
```

## 响应参数

| 参数 | 类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| page | string | 页码 | 2 |
| pageSize | string | 一页显示几条 | 10 |
| total | string | 总条数 | 100 |
| id | string | 活动 ID | 8050309 |
| name | string | 活动名称 | 分享禁用测试活动 |
| status | string | 活动状态 | enabled |

## 响应示例

```javascript
{
    "pager": {
        "page": 1,
        "pageSize": 10,
        "total": 16
    },
    "items": [
        {
            "id": "2837888",
            "name": "创想人工智能峰会-深圳站",
            "categoryId": 1,
            "status": "disabled",
            "agentId": 101691,
            "startedAt": "2018-01-29T06:58:26.000Z",
            "endedAt": "2018-01-29T10:58:26.000Z",
            "pushDomain": "push.shangzhibo.tv",
            "pullDomain": "play.shangzhibo.tv",
            "isPushing": false,
            "createdAt": "2018-01-29T05:58:28.000Z",
            "updatedAt": "2018-01-29T11:09:35.000Z",
            "app": "r1g3-d43BM",
            "stream": "Hkb3WOE2BM",
            "isPrologueEnabled": true,
            "isEpilogueEnabled": true,
            "isBackupRecordEnabled": false,
            "isLiveEnabled": true,
            "fake": {
                "baseCount": 0,
                "increaseMin": 1,
                "increaseMax": 1
            },
            "isFakeEnabled": false,
            "isFilterAllEnabled": false,
            "filterIpList": {},
            "filterSidList": {},
            "filterUserList": {},
            "isRobotEnabled": false,
            "robot": {
                "initialCount": 10,
                "incrementCount": 1
            },
            "expired": false,
            "maxConcurrentUser": -1,
            "maxPushingTime": -1,
            "subagentIds": [1, 2],
        }
    ]
}
```

