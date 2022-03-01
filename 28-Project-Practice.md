[[J網站開發程序]]

---

##### [[J0 建構環境]] 

J0.1 Visual Studio

J0.1.1 Code Extension in Visual Studio

##### [[J1 建構 Express]]

**J1.1 Create Project Folder ** 

`/Users/youjhen-ming/Downloads/AllCategories/_Programming/_Javascript/28-Website-Practice`

##### [[J0 建構環境]]

**J0.2 init express**

**J0.3 package.json**

```
{
  // ...
  "main": "app.js",
  "scripts": {
    "start": "node app.js",
    "dev": "nodemon app.js",
    "test": "echo \"Error: no test specified\" && exit 1"
    "seed": "node models/seeds/recordSeeder.js"
  },
  //...
}
```

Check `$ npm run dev` works

**J0.4 Git init**

`$ git init`

**J0.4.2 設定 Git 使用者名稱和信箱**

// 設定名稱和信箱

```
$ git config --global user.name "elliotyou"
$ git config --global user.email "m9402311@mail.ntust.edu.tw"
```

// 確認設定成功

```
$ git config --list
credential.helper=osxkeychain
user.name=elliotyou
user.email=m9402311@mail.ntust.edu.tw
```

**J0.4.3 .gitignore**

`$ touch .gitignore` 並修改內容

```
/node_modules
.DS_Store
```

**J1.2 Create Basic Express**

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

`$ node app.js` 確認正常

`$ nodemon app.js` 確認正常

`http://localhost:3000` 確認有通

##### [[J2 建構 Handlebars]]

J2.1 下載 express-handlebars

**J2.2 app.js 中套用**

```js
...
...
const engine = require('express-handlebars')
...
...
const { engine } = require('express-handlebars')

app.engine('hbs', engine({ defaultLayout: 'main', extname: '.hbs' }))  

app.set('view engine', 'hbs')
```

[[2022-02-27 (日)]] 實做時發現有異動，參考 [StackOverflow]([javascript - TypeError: exphbs is not a function - Stack Overflow](https://stackoverflow.com/questions/69959820/typeerror-exphbs-is-not-a-function))

**J2.3 Create views folder**

`$ code views/layouts/main.hbs`

```html
<!-- ./views/layouts/main.handlebars -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>
  <!-- partial templates will replace the part of "body" here -->

  {{{ body }}}

</body>
</html>
```

**J2.4 新增一個 index.hbs 開始編輯**

`$ code views/index.hbs` → 僅放入 this is my first website 字樣

`$ code app.js`

```js
app.get('/', (req, res) => {
  res.render('index')
})
```

確認執行正常

##### [[J3 建構 Bootstrap]]

**J3.1 Apply CDN in main.hbs**

From Bootstrap website →  Getting Started → Download → CDN

```html

<head>
...
...
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"integrity="sha384EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
</head>

<body>
  ...
  ...
  ...
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
  <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js" integrity="sha384-IQsoLXl5PILFhosVNubq5LC7Qb9DXgDA9i+tQ8Zj3iwWAwPtgFTxbJ8NT4GN1R8p" crossorigin="anonymous"></script>
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.min.js" integrity="sha384-cVKIPhGWiC2Al4u+LWgxfKTRIcfu0JTxR+EQDz/bgldoEyl4H0zUF0QKbrJ0EcQF" crossorigin="anonymous"></script>
</body>
```

套一下 Bootstrap 的 button 樣板，確認可以看得到 bootstrap 效果

```html
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
```

##### [[J4 建構 FontAwesome]]

**J4.1 Apply FontAwesome CDN**

進到 [FontAwesome 管理頁面](https://fontawesome.com/sessions/sign-in?next=%2Fkits)

點進去這裡

<a href="https://imgur.com/KDU0h5V"><img src="https://i.imgur.com/KDU0h5V.jpg" title="source: imgur.com" width="600px"/></a>

複製 Kit Code，貼到

```html
<head>
  ...
  ...
  <script src="https://kit.fontawesome.com/a8003775e6.js" crossorigin="anonymous"></script>
</head>
```

[[2022-02-27 (日)]] 遇到奇怪的狀況，CDN 都套對了，font awesome 的基本 icon 秀不出來，就連在 codepen 上也是一樣的結果，暫時找不到原因


##### [[J5 建構 HTML]]

**J5.1 Apply a Form Example** 

套用 HTML 範例 [Random Password Generator](https://codepen.io/elliotyou/full/QWvPJLQ) 來確認是否畫面正常呈現

##### [[J6 建構 MongoDB]] 

**J6.2 Run MongoDB** [[2022-02-28 (一)]]

開一個獨立的 terminal，進到 mongodb/bin，重啟 mondodb，將它開著不動

`./mongod --dbpath /Users/youjhen-ming/mongodb-data`

**J6.3 Create Database**

打開 robo 3T → create database → 取名 todo-list

**J6.4 Check  DB Connection**

`$ npm i mongoose`

app.js 加入

```js
const mongoos = require('mongoose')
mongoose.connect('mongodb://localhost/todo-list') // 讓 mongoose 連線，這裡的 todo-list 指的是 db 的
```

```js
const db = mongoose.connection

db.on('error', () => {
  console.log('mongodb error!')
})

db.once('open', () => {
  console.log('mongodb connected!')
})
```

`$ npm run dev`

確定有成功run起來，有看到 mongodb connected

**J6.6 Create Basic Seeders**

建 Schema

`$ code model/todo.js`

```js
const mongoose = require('mongoose')
const Schema = mongoose.Schema

const todoSchema = new Schema({
  name: {
    type: String,
    required: true,
  }
})

module.exports = mongoose.model('Todo', todoSchema)
```

建 seeder

`$ code models/seeds/todoSeeder.js`

重複一些剛剛的東西

```js
const mongoose = require('mongoose')

mongoose.connect('mongodb://localhost/todo-list', { useNewUrlParser: true, useUnifiedTopology: true }) 

const db = mongoose.connection

db.on('error', () => {
  console.log('mongodb error!')
})

db.once('open', () => {
  console.log('mongodb connected!')
})
```

新增 

```js
const Todo = require('../todo')
```

進到 db.once

```js
console.log('mongodb connected!')
for ( let=0; i<10; i++ ){
  Todo.create({ name: `name-${i}` })
}
console.log('done.')
```

執行 `$ node models/seeds/todoSeeder.js`

會看到 mongledb connect 以及 done. 的字樣

Robo 3T 查看剛剛的 Todo DB，collections中有出現了我們剛新增的東西

將腳本改為如下：

```
"scripts": {
    "start": "node app.js",
    "dev": "nodemon app.js",
    "test": "echo \"Error: no test specified\" && exit 1",
    "seed": "node models/seeds/todoSeeder.js" // 新增腳本
  },
```

##### [[J1 建構 Express]]

**J1.3 READ of CRUD** - 列出大概

`$ code app.js` 

```js
const Todo = require('./models/todo')
```

進到 app.get

```js
Todo.find()
  .lean()  //mongo額外的東西拿掉
  .then(todos => res.render('index', { todos }))
  .catch(error => console.error(error))
```

`$ npm run dev`

確定看到 list 0~9 ，只差順序不一致

##### [[J2 建構 Handlebars]]

**J2.5 Basic Each Syntax**

進到 index.hbs

```html
<ul>
  {{#each todos}}
  <li>{{this.name}}</li>
  {{/each}}
</ul>
```

##### [[J1 建構 Express]]

**J1.4 CREATE of CRUD**

`$ code views/new.hbs` // 準備好一個 FORM 用到的頁面

```html
<form action="/todos" method="POST">
	<input type="text" placeholder="name" name="name">
	<button type="submit">Create</button>
</form>
```

`$ code views/index.hbs` // 準備一個按鈕

```html
<a href="./todos/new">Create</a>
```

`code app.js` // 修改 route

```js
app.get('/todos/new', (req, res) => {
  return res.render('new')
})
```

```js
app.post('/todos', (req, res) => {
  const name = req.body.name
  const todo = new Todo({ name })
  return todo.save()
    .then(() => res.redirect('/'))
    .catch(err => console.log(err))
})
```

`# npm run dev` // 出現了一個Create的按鈕，可以用來新增

執行 post 會有error
`TypeError: Cannot read property 'name' of undefined`

這時候需要一個東西叫 body-parser

`npm i body-parser`

回到 app.js

```js
...
...
const bodyParser = require('body-parser')
...
...
app.use(bodyParser.urlencoded({ extended: true }))
```

`$ code app.js` 優化，兩者寫法是等價的

```js
const name = req.body.name
return Todo.create({ name })
  .then(()=>res.redirect('/'))
  .catch(error => console.log(error))
```

##### [[J1 建構 Express]]

**J1.3 READ of CRUD** - 讀取各別 item

`$ code views/index.hbs`

```html
{{#each todos}}
  <li>
    {{this.name}} <!-- 改這裡 -->
    <a href="./todos/{{ this._id }}">detail</a> <!-- 改這裡 -->
  </li>
{{/each}}
```

`$ code app.js`

```js
app.get('/todos/:id', (req, res) => {
  const id = req.params.id
  return Todo.findById(id)
    .lean()
    .then(todo => res.render('detail', { todo }))
    .catch(error => console.log(error))
})
```

`$ code views/detail.hbs`

```html
<p>{{ todo.name }}</p>
<a href="/">back</a>
```

`npm run dev`

後面多了 detail 可以點，點下去以後有內容，也可以back

##### [[J1 建構 Express]]

**J1.5 UPDATE of CRUD**

`$ code views/index.hbs` → 新增編輯按鈕

```html
...
<a href="/todos/{{ this._id }}/edit">edit</a>
```

`$ code views/detail.hbs` → 新增編輯按鈕

```html
<a href="/todos/{{ todo._id }}/edit">edit</a>
```

`$ code app.js`  → 建立一個 /edit 的路由，會跟detail很像

```js
app.get('/todos/:id/edit', (req, res) => {
  const id = req.params.id
  return Todo.findById(id)
    .lean()
    .then(todo => res.render('edit', { todo }))
    .catch(error => console.log(error))
})
```

`$ code views/edit.hbs` 後編輯

```html
<form action="/todos/{{ todo._id }}" method="POST">
	<input type="text" placeholder="name" name="name" value="{{ todo.name }}">
	<button type="submit">Save</button>
	<a href="/">back</a>
</form>
```

`$ code app.js` → 新增一個路由在app.js

```js
app.post('/todos/:id', (req, res) => {
  const id = req.params.id
  const name = req.body.name // 這裡的 name 會跟 html中 input 標籤裡的 name="" 對應
  return Todo.findById(id)
    .then(todo => {
      todo.name = name
      return todo.save()
    })
    .then(() => res.redirect(`/todos/${id}`))
    .catch(error => console.log(error))
})
```

`$ npm run dev` → 實測結果

