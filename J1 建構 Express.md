[[J網站開發程序]]

---

[[28-Project-Practice]]


---

### J1.1 Create Project Folder

### J1.2 Create Basic Express

### J1.3 READ of CRUD

```js
Todo.find()
  .lean()  // data 額外的東西拿掉
  .then(todos => res.render('index', { todos }))
  .catch(error => console.error(error))
```

### J1.4 CREATE of CRUD
- 讀取大概
- 讀取各別 item

### J1.5 UPDATE of CRUD

### J1.6 DELETE of CRUD

