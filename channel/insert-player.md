## 获取播放器嵌入

###接口
获取播放器嵌入

```js
GET /activity/{id}/iframe
```
###授权
无需授权

###参数

param | type | name | example
- | - | - | -
type | 	string ``Required`` | 嵌入类型 | valid values: 'playeronly''full'<br>嵌入类型playeronly 仅播放器嵌入 full 完整嵌入
width | integer | 播放器宽 | 1080
isPushing | boolean | 是否在推流 | true
height | integer | 播放器高 | 720

####样例

```js
/activity/{id}/iframe?type=playeronly&width=42&height=42
```

###响应

param | type | name | example
- | - | - | -
code | string | 嵌入代码 | -

```js
{
  "code": "stringValue"
}
```


