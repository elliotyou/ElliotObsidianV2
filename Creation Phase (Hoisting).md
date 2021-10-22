From: [[Javascript 重要觀念]]

---

當你這樣寫的時候，b 會正常跑，a 會是 undefined

```js
b()  //Called b!
console.log(a) //undefined

var a = 'Hello World!'

function b(){
  console.log('Called b!')
}
```


但如果你連下方的 var a 都沒寫，他跑起來的結果是 'a is not defined'

```js
b()   //Called b!
console.log(a) //Error: a is not defined
function b(){ 
  console.log('Called b!') 
}
```


有的人會說，因為 javascript 其實幫你把 code 改成下方這樣

```js
function b(){ 
  console.log('Called b!') 
}
var a

b() 
console.log(a) 
a = 'Hello World!' 
```


但實際上 javascript 並沒有去改動你的 code，他只是在逐行執行你的 code 之前，還有一個動作 **Creation Phase (Hoisting)**

<a href="https://imgur.com/PzGmEW4"><img src="https://i.imgur.com/PzGmEW4.jpg" title="source: imgur.com" width="600px" /></a>

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