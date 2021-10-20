From: [[Javascript 重要觀念]]

---

<a href="https://imgur.com/PzGmEW4"><img src="https://i.imgur.com/PzGmEW4.jpg" title="source: imgur.com" width="600px" /></a>

逐行跑code之前，會先經過此階段 **Creation Phase (Hoisting)**

在 Hoist 階段，Javascript 會先掃過所有你的宣告 ( variable / function )，然後先為它們保留一個 memory 位置

有被保留 memory 的 variable ，其值會先被指定為 [[undefined]] 

因此 undefined 和 is not defined 是不一樣的
* **undefined**: 電腦有保留 memory 給這個 variable ，但還沒被定義過裡面是什麼，這不是 error
* ** is not defined**: 電腦並沒有保留 memory 給這個 variable ，這是 error

下方這樣的做法也是合法的，但請千萬不要這麼做。

```js
var a = 'Hellow World!'
console.log(a)

a = undefined   //自己手動改回去 undefined

if (a === undefined) {
  console.log('a is undefined')
} else {
  consooe.log('a is defined')
}
```

因為 undefined 就是用來讓人知道這個 variable 經過的 creation 階段只是還沒有給它值

如果你有可能手動改回去 undefined ，那下次你看到一個 variable 是 undefined 的時候，你搞不清楚是人為故意的還是不小心的