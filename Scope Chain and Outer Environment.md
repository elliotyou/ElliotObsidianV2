From: [[Javascript 重要觀念]]

---

### Outer Environment

```js
function b(){
  console.log(myVar)
}

function a(){
  var myVar = 2
  b()
}

var myVar = 1
a()  //1
```
   
上面的結果，直覺會是 undefined 才對，因為 b() 的 Execution Context 中並沒有宣告過 myVar

但實際執行後的結果是 1

因為 Javascript 有個 Scope Chain 的機制，是他在當前 Execution Context 中找不到該 variable 的宣告時，會去 **Outer Environement** 找有沒有這個 vairable ，若的的話，就還是會抓來用

而以上述的範例來說，a 和 b 的outer environment 就是 global context

雖然 b 被放到 a 裡呼叫(invoke)，但其實是要看`他們宣告的位置`，他們都是在 Global Context 中宣告，所以他們 2 個的 outer environment 都是 Global Context

<a href="https://imgur.com/ZRrBXeZ"><img src="https://i.imgur.com/ZRrBXeZ.jpg" title="source: imgur.com" width="500px" /></a>

### Scope Chain

如果將 code 改成這樣：

```js
function a(){
  function b(){
    console.log(myVar)
  }
  var myVar = 2
  b()
}
var myVar = 1
a()  //2
```

則 console.log 的會是 2 ，因為此時 b 的 outer environment 變成 a，而 a 裡有個 myVar = 2

若再將 a 裡的 var myVar = 2 移掉如下

```
function a(){
  function b(){
    console.log(myVar) 
  }
  b()
}

var myVar = 1
a()
```

則 console.log 會是 1，它會再往外找，直到沒辦法找為止，這個機制就是 Scope Chain

<a href="https://imgur.com/Nt7KIyf"><img src="https://i.imgur.com/Nt7KIyf.jpg" title="source: imgur.com" width="500px"/></a>