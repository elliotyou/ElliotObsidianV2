From: [[Execution Phase]]

---

首先第一個必產生的是 Global Execution Context，它的 Outer 會是 Null

如果你什麼都沒寫，光是在瀏覽器上跑一個空的 js，就會看到有 this 這個東西

<a href="https://imgur.com/gWXJaUh"><img src="https://i.imgur.com/gWXJaUh.png" title="source: imgur.com" /></a>

此時的 Execution context 長這樣，它就是 Global Execution Context

<a href="https://imgur.com/WF9FAKq"><img src="https://i.imgur.com/WF9FAKq.png" title="source: imgur.com" width="400px"/></a>

> **Global** 
Not inside a Function

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