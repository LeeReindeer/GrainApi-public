# GrainApi-public



> RESTful api for [Grain](https://github.com/LeeReindeer/Grain)
>
>Write in go, and is closed sourse.
## 使用-Usage

### Get

- `/api/search?type=<t>&user=<userId>&token=<your token>`

- type: mark/course/book/consum
- user: 一般为你的学号
- token: 从服务器获取的token(当你从不同的设备登录时，上一个token会失效，你必须重新获取token，获取的方式是发送 `POST` 请求。)

- 例子： `/api/search?type=mark&user=171303204&token=TOKEN`
- 返回：

```json
{
  "code":200,
  "data":[{"..."},{"..."}],
  "total":2
}
```

### Post

- `/api/token`

- 数据格式: `json`
- 强制要求： `queryType` 必须为 `Validation`。
- 例子： 

```json
{
"data":
	{
		"queryType":"Validation",
		"schoolId":"171303204",
		"token":"",
		"name":"**",
		"pass":"*********",
		"extend":"171303204",
		"hostInfo":""
	}
}
```

- 返回：

```
{
"code": 200,
"token": "token"
}
```

## 全局错误代码 - Error code

- 200: 正常

- 404: 网络错误
- 403：连接超时

- 110：token错误
- 109：密码错误

...

## License

GPL
