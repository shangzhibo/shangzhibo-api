---
description: （仅移动端展示）
---

# 添加自定义悬浮菜单

## 接口

添加自定义悬浮菜单

```javascript
PUT /api/activity/{id}/promotions
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: application/json
```

注：请将上方的`<accessToken>`替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| title | string | 菜单名称 | 否 |
| url | string | 菜单跳转地址 | 是 |
| image | string | 菜单图标地址 | 是 |
| label | string | 菜单类型，此处填写 float | 是 |

### 请求样例

```javascript
[
    {
        "title":"测试悬浮菜单",
        "url":"http://shangzhibo.tv",
        "image":"http://doc.shangzhibo.tv/test/512%20(1).png",
        "label":["float"]
    }
]
```

## 请求样例

```text
/api/activity/1943608/promotions
```

## 响应参数

无

## 响应示例

```text
{
  "result": true,
}
```

