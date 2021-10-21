From: [[Javascript 重要觀念]]

---

結束 [[Creation Phase (Hoisting)]] 以後，程式會進到 [[Execution Phase]]

### Execution Phase

在這個階段，code 都會被一塊塊的 Execution Context 所執行， Execution Context 的結構長這樣

### Execution Context

<a href="https://imgur.com/wxOfRi9"><img src="https://i.imgur.com/wxOfRi9.png" title="source: imgur.com" width="600px"/></a>

Global Object: 在 browser 中就是 window object
this: 參考 [[Javascript 中的 this]]
Variable: Memeory 中的一個位置，存放所有在此環境下存活的變數
Outer: 

### Global Execution Context

首先第一個必產生的是 Global Execution Context，它的 Outer 會是 Null

如果你什麼都沒寫，光是在瀏覽器上跑一個空的 js，就會看到有 this 這個東西

<a href="https://imgur.com/gWXJaUh"><img src="https://i.imgur.com/gWXJaUh.png" title="source: imgur.com" /></a>

此時的 Execution context 長這樣，它就是 Global Execution Context

<a href="https://imgur.com/WF9FAKq"><img src="https://i.imgur.com/WF9FAKq.png" title="source: imgur.com" width="400px"/></a>

**Global** 的定義就是 Not inside a Function

來寫個基本的 code

```js
var a = 'Hello World'
function b(){
}
```

你宣告過的東西，都會自動被放到這個 Global Object 裡面

<a href="https://imgur.com/4ZbLKGQ"><img src="https://i.imgur.com/4ZbLKGQ.png" title="source: imgur.com" width="600px" /></a>

你也可以直接 windows.a 呼叫到它

<a href="https://imgur.com/gxla1UK"><img src="https://i.imgur.com/gxla1UK.png" title="source: imgur.com" width="600px"/></a>

### Execution Stack

接下來如果有 Function 被 invoke ，就會再疊一個該 Function 的 Execution Context 上去

