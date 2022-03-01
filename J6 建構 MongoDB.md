[[J網站開發程序]]

---

[[28-Project-Practice]]

---

### J6.1 安裝 MongoDB (macOS)

### J6.2 Run MongoDB

開啟 terminal，進到 mongodb/bin，重啟 mondodb，將它開著不動

`./mongod --dbpath /Users/youjhen-ming/mongodb-data`

### J6.3 Create Database

打開 robo 3T → create database → 取名 todo-list

### J6.4 Check  DB Connection

 `$ npm i mongoose`

在 app.js 中加入 連線 mongoose, db.on, db.once

確認 `$ npm run dev` 有看到 mongodb connected

### J6.5 Adjust the Warnings

有看到2個 warning，2個東西被棄用，需要調整

```
mongoose.connect('mongodb://localhost/todo-list', { useNewUrlParser: true, useUnifiedTopology: true }) 
```

再重啟一次，確定剛剛的兩個 warning 不見了

### J6.6 Create Basic Seeders

