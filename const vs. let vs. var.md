From: [[Javascript 重要觀念]]

---

### Case1. 宣告而不給值

var
```js
var a
console.log(a) //undefined
```

let
```js
let a
console.log(a) //undefined
```

const
```js
const a
console.log(a)  //SyntaxError: Missing initializer in const declaration

```

結論:  const 在一宣告時就必定要指定值，不然會報錯；而 var 和 let 可以在宣告的時候不給值，如果這麼做，會自動被定義為 undefined

---
### Case2. 宣告為 Number 後，改變其值
var
```js
var a = 3
a = 5
console.log(a)  //5
```

let
```js
let a = 3
a = 5
console.log(a)  //5
```

const
```js
const a = 3
a = 5
console.log(a) //TypeError: Assignment to constant variable.
```

結論: var 與 let 允許被修改；而 const 不允許被修改

---

### Case3. 在 [[區塊 (Code Block)]] 內宣告
var
```js
if (true){
  var a = 3
}
console.log(a)  //3
```

let
```js
if (true){
  let a = 3
}
console.log(a)  //ReferenceError: a is not defined
```

const
```js
if (true){
  const a = 3
}
console.log(a) //ReferenceError: a is not defined
```

結論: var 在 code block 內宣告，等同於在 block 外宣告；而 let 和 const 則只存活在 code block 中。因此 var 會有 污染全域變數 的風險

---

### Case4. 在 Global 重複宣告

var + var
```js
var a = 2
var a = 6
console.log(a)  // 6
```

let + var
```js
let a = 2
var a = 6
console.log(a)  // SyntaxError: Identifier 'a' has already been declared
```

var + let
```js
var a = 2
let a = 6
console.log(a)  // SyntaxError: Identifier 'a' has already been declared
```

let + let
```js
let a = 2
let a = 6
console.log(a)  // SyntaxError: Identifier 'a' has already been declared
```

const 的結果同 const

結論: 只有 var + var 是被允許的，且第2次宣告時會將第1次的值 overwrite。其餘 var 和 let/const 的混用結果都是不被允許宣告兩次的。

---

### Case5. Global 與 Code Block 分別宣告

var
```js
var a = 10
console.log(a)    //10
{
  a = 20
  console.log(a)  //20，此時的 a 跟上面同一個
}
console.log(a)    //20
```

```js
var a = 10
console.log(a)    //10
{
  var a = 20
  console.log(a)  //20 重複宣告，與 Code Block 特性同時產生效果
}
console.log(a)    //20
```

let
```js
let a = 10
console.log(a)    //10
{
  a = 20
  console.log(a)  //20，此時的 a 跟上面同一個
}
console.log(a)    //20
```

```js
let a = 10
console.log(a)    //10
{
  let a = 20
  console.log(a)  //20，此時的 a 是另一個，只存活在 code block 內
}
console.log(a)    //10
```

結論: Code Block 內宣告變數時，若用 var 則等同於在 Block 外宣告；若用 let/const 則不管 Block 外有沒有宣告過，都會再開一個新的變數出來。而不宣告，JavaScript 也會往外層尋找是否有 a 宣告過