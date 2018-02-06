## 获取指定活动播放器嵌入代码

### 接口

获取播放器嵌入

```js
GET /api/activity/{id}/iframe
```

### 授权

无需授权

### 参数

| 参数 | 参数类型 | 参数说明 | 是否必填 |
| --- | --- | --- | --- |
| type | string | 嵌入类型，取值：`playeronly` 仅播放器嵌入  `full` 完整嵌入 | 是 |
| width | integer | 播放器宽，仅在嵌入类型是 `playeronly` 模式时有效 | 否 |
| height | integer | 播放器高，仅在嵌入类型是 `playeronly` 模式时有效 | 否 |

#### 请求样例

```js
/api/activity/8930091/iframe?type=playeronly&width=640&height=360
```

### 响应

| 参数 | 参数类型 | 参数说明 |
| --- | --- | --- |
| code | string | 嵌入的代码 |

#### 响应样例

```js
{
  "code": "<iframe
           src=\"http://shangzhibo.tv/watch/${activity.id}?player\"
           style=\"width: 640px; height: 360px; overflow:hidden;\"
           scrolling=\"no\" allowFullScreen>
          </iframe>"
}
```



