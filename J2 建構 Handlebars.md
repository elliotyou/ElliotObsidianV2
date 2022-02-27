[[J網站開發程序]]

---

[[28-Project-Practice]]

---

## J2.1  下載  express-handlebars

`$ npm i express-handlebars`

## J2.2 app.js 中套用

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

## J2.3 Create views folder

在專案資料夾中，建一個 views 資料夾 ， 再 views 中再建一個 layouts

```
$ mkdir views
$ cd views
$ mkdir layouts
```

layouts 資料夾中放 main.hbs。 main 內容如下：

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

而其中 {{{body}}} 的那一段，都會在 views 裡面

每次 render views 中的 1 個 page，都會是 main + page 概念

## J2.4 新增一個 index.hbs 開始編輯

在 views 中新增一個 index.hbs 開始編輯

將 route 內容修改：

```js
app.get('/', (req, res) => {
  res.render('index')
})
```


---

參考資料: 
- [Using template engines with Express (expressjs.com)](https://expressjs.com/en/guide/using-template-engines.html)