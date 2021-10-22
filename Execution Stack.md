From: [[Execution Phase]]

---

接下來如果有 Function 被 invoke ，就會再疊一個該 Function 的 Execution Context 上去

下方給出一個例子

 ```js
 function b(){
}
function a(){
  b()
}
a()
 ```

當呼叫到 a() 的時候，會先疊一個 a() 的 execution context 在 global 上方，因為 a() 裡又 invoke b()，因此又會再疊一個 b() 的 executio context，型成像下方這樣的概念

<a href="https://imgur.com/FvGbPn3"><img src="https://i.imgur.com/FvGbPn3.jpg" title="source: imgur.com" width="400px"/></a>

再舉一個例子：

```js
function a(){
  b()
  var c
}
function b(){
  var d
}
a()
var d
```

他的執行過程是：
- 先有一個 Global Execution Context
- 執行到 a() ，疊一個 a() 的 Execution  Context 上去
- a() 裡有 b() ，再疊一個 b() 的 Execution Context
- b() 裡新增 var d
- b() 結束，b() 的 Execution context 消失
- 執行 a() 裡的 var c
- a() 結束，a() 的 Execution Context 消失
- 執行 Global 的 var d

<a href="https://imgur.com/A8pURm9"><img src="https://i.imgur.com/A8pURm9.jpg" title="source: imgur.com" width="400px"/></a>