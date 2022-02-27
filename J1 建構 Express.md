[[J網站開發程序]]

---

[[28-Project-Practice]]


---

## J1.1 Create Project Folder

## J1.2 Create Basic Express

```js
const express = require('express')
const app = express()
const port = 3000 // 指定 port

app.get('/', (req,res) => { // 設一個最基本 route
  res.send('this is my first web')
})

app.listen(port, () => { // 啟動監聽 server
  console.log(`Express is running on http://localhost:${port}`)
})
```

$ node app.js 測試執行

$ nodemon app.js 測試執行

確認 `http://localhost:3000` 有通
