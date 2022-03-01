[[J網站開發程序]]

---

[[28-Project-Practice]]

---

### J2.1  下載  express-handlebars

`$ npm i express-handlebars`

### J2.2 app.js 中套用

### J2.3 Create views folder

### J2.4 新增一個 index.hbs 開始編輯

### J2.5 Basic Each Syntax

進到 index.hbs

```
<ul>
  {{#each todos}}
  <li>{{this.name}}</li>
  {{/each}}
</ul>
```