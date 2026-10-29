# random-api-jokes —— 随机笑话 API

一个用 Flask 写的极小后端 demo：浏览器访问网址，服务器从内存笑话库里按你定义的规则返回数据。

## 功能

| 接口 | 说明 |
|------|------|
| `GET /` | 首页，接口目录 |
| `GET /api/joke/random` | 随机返回一条笑话（JSON） |
| `GET /api/jokes` | 返回全部笑话和总数 |
| `GET /api/joke/<id>` | 按 id 查单条；不存在返回 404 |
| `GET /api/joke/count` | 返回笑话总数 |
| `GET /play` | 网页版：一个"再来一个"按钮，前端 fetch 调用上面的接口 |

## 运行

需要 Python 3.10+：

```bash
pip install flask pytest
python app.py
# 浏览器打开 http://localhost:5050
```

## 测试

```bash
pytest -v
```

## 技术栈

Python · Flask 3 · pytest · 原生 HTML + JS

## 说明

- 数据持久化在 `jokes.json`：首次运行由代码中的种子数据生成，之后所有投稿都写入该文件，**服务器重启不丢失**
- `jokes.json` 是运行时数据，不纳入 git（已在 .gitignore）
- 自带 debug 模式（改代码保存后自动重启），是开发服务器，请勿直接用于生产
- 联系方式：（占位）your-email@example.com
