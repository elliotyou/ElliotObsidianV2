[[J網站開發程序]]

---

### 4.1 Apply FontAwesome CDN

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
