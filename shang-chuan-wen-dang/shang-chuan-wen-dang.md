---
description: 该接口已废弃
废弃原因: >-
  该接口是同步接口，经常会出现接口超时而拿不到转码数据的问题。建议使用新的[异步接口](shang-chuan-wen-dang/shang-chuan-wen-dang-v2-1.md)
---

# 上传文档 V1

## 废弃原因: 

#### 该接口是同步接口，经常会出现接口超时而拿不到转码数据的问题。建议使用新的[异步接口](https://document.shangzhibo.tv/api/shang-chuan-wen-dang/shang-chuan-wen-dang-v2-1)

## 接口

上传文档

```javascript
POST /api/activity/:id/doc
```

## 授权

请求 header

```http
Authorization: Bearer <accessToken>
Content-Type: multipart/form-data
```

注：请将上方的 `<accessToken>` 替换为分配给您的秘钥串。关于如何获取 accessToken ，请咨询杨经理（18968187008）、彭经理（15167172618）。

## 参数

无

### 请求样例

```bash
curl http://shangzhibo.tv/api/activity/:id/doc -F file=@test.pptx
```

## 响应

HTTP/1.1 200 OK

### 响应样例

```javascript
{
    "basePath":"https://shangzhibo-img.b0.upaiyun.com/client/activity/2929745/doc/1555642339828",
    "originalname":"test.pptx",
    "filename":"229c988d45ce0222bd5e710056a58de7.pptx",
    "pageCount":11,
    "currentPage":0
}
```

