From: [[Execution Context]]

---

**Variable Environment**:
Where the variables live. And how they relate to each other in memory

Memeory 中的一個位置，存放所有在此環境下存活的變數

範例：
```js
function b(){
  var myVar
}
function a(){
  var myVar = 2
  b()
}
var myVar = 1
a()
```

雖然看起來都是 myVar，但其實分別屬於 3 個完全不同的 Execution Context，各自都有 1 個 myVar 在裡面，且值各不同  

因此它也會各自佔掉該佔的 memory ，完全是獨立的 3 個東西

<a href="https://imgur.com/6sgTYn7"><img src="https://i.imgur.com/6sgTYn7.jpg" title="source: imgur.com" width="400px"/></a>