# ⚡ JavaScript Quick-Reference Cheat Sheet (ES5-Era, No ES6)
---

## 1️⃣ Statements & Declarations

```js
// Standard statement – always finish with ;  ✅ best practice
alert("Hi");                         // => (modal alert)

/* Variable keywords */
var globalVar = 1;                   // function-scope ✔
letBlock = 2;                        // ES5 has no let – mimic via IIFE
const PI = 3.14;                     // const (ES6) unavailable; use var + UPPERCASE

// Mimic block-scoped variable with IIFE
(function () {
  var inner = "private";
  // inner is inaccessible outside
})();
```

**Best Practice:** In legacy ES5, use `var` but limit scope with **functions/IIFEs** to avoid leaks.
---
IIFEs = Immediately Invoked Function Expression 
---

## 2️⃣ Data Types & Type Conversion

```js
typeof 42;               // => "number"
typeof "abc";            // => "string"
typeof false;            // => "boolean"
typeof undefined;        // => "undefined"
typeof null;             // => "object"  // quirky JS behavior
typeof {};               // => "object"
typeof [];               // => "object"  // arrays are objects

// Conversion
Number("123");           // => 123
parseInt("FF", 16);      // => 255
String(99);              // => "99"
Boolean(0);              // => false
!!"text";                // => true   (shorthand truthiness)
```

**Best Practice:** Prefer **`Number()` over `parseInt`** unless radix needed. Always supply radix to `parseInt`.

---

## 3️⃣ Operators (Arithmetic ➕, Comparison ❓, Logical &&)

```js
5 + 2;              // => 7
5 - 2;              // => 3
5 * 2;              // => 10
5 / 2;              // => 2.5
5 % 2;              // => 1
Math.pow(2,3);      // => 8   (ES5 alternative to **)

// Assignment
var x = 10;
x += 3;             // x => 13

// Comparison – use strict
3 === "3";          // => false
3 !== "3";          // => true

// Logical
true && false;      // => false
true || false;      // => true
!0;                 // => true  (0 is falsy)
```

**Best Practice:** **Always** use `===` / `!==`.

---

## 4️⃣ Control Flow

```js
// if / else
if (score >= 90)        grade = "A";
else if (score >= 80)   grade = "B";
else                    grade = "C";

// Switch
switch (key) {
  case 1: result = "one"; break;
  case 2:                       // fall-through
  case 3: result = "two-or-three"; break;
  default: result = "other";
}

// Ternary shorthand
var vote = (age >= 18) ? "Yes" : "No";   // => "Yes" or "No"
```

---

## 5️⃣ Loops & Iteration

```js
for (var i = 0; i < 3; i++) console.log(i);  // => 0 1 2
var j = 3;
while (j--) console.log(j);                 // => 2 1 0

// break / continue
for (var n = 0; n < 5; n++) {
  if (n === 2) continue;   // skip 2
  if (n === 4) break;      // stop loop
  console.log(n);          // => 0 1 3
}

// Array iteration
[1,2,3].forEach(function(v,i){ console.log(i,v); });
// => 0 1 | 1 2 | 2 3
```

**Best Practice:** Prefer **`.forEach` / `.map`** for readability; reserve classic `for` for performance-critical paths.

---

## 6️⃣ Functions, Scope & `this`

```js
// Declaration (hoisted)
function add(a,b){ return a+b; }
add(2,3);                            // => 5

// Expression
var mul = function(a,b){ return a*b; };

// IIFE (Immediately-Invoked Function Expression)
var module = (function(){
  var private = 42;
  return { get: function(){ return private; } };
})();
module.get();                        // => 42

// call / apply / bind
add.call(null,2,3);                  // => 5
add.apply(null,[2,3]);               // => 5
var add2 = add.bind(null,2); add2(8);// => 10

// Closure counter example
function makeCounter(){
  var c = 0;
  return function(){ return ++c; };
}
var inc = makeCounter();
inc(); inc(); inc();                 // => 1 2 3

// 'this' depends on call site
var o = {val:7, get:function(){ return this.val; }};
o.get();                             // => 7
var loose = o.get;                   // detached – this === global / undefined
```

**Best Practice:** Always **capture `this`** (`var self = this`) or use `.bind` when passing callbacks.

---

## 7️⃣ Objects & Prototypes

```js
// Literal
var user = {name:"Sara", age:28};
user.city = "Cairo";                 // add property

// Constructor pattern
function Person(name){
  this.name = name;
}
Person.prototype.say = function(){return "Hi "+this.name;};

var p = new Person("Ali");
p.say();                             // => "Hi Ali"

// Inheritance with Object.create
var admin = Object.create(p);
admin.role = "Admin";
admin.say();                         // => "Hi Ali"
```

**Best Practice:** Don’t modify `Object.prototype`; extend via your own constructors or `Object.create`.

---

## 8️⃣ Arrays – Power Toolkit

```js
var arr = [3,1,4];

// CRUD
arr.push(2);           // => 4 (new length)
arr.pop();             // => 2 (removed value)
arr.shift();           // => 3 (removed head)
arr.unshift(9);        // => 4 (new length), arr=[9,1,4]

// Slice / Splice
arr.slice(1);          // => [1,4] (non-mutating)
arr.splice(1,1,"X");   // => ["1"] (removed), arr=[9,"X",4]

// Search / Test
arr.indexOf("X");      // => 1
arr.lastIndexOf(4);    // => 2
arr.join("-");         // => "9-X-4"
[1,2,3].every(function(n){return n>0;}); // => true

// Map / Filter / Reduce
[1,2,3].map(function(n){return n*2;});   // => [2,4,6]
[1,2,3].filter(function(n){return n>1;});// => [2,3]
[1,2,3].reduce(function(a,b){return a+b;},0); // => 6
```

**Shorthand push:** `arr[arr.length] = value;` (slightly faster, rarely needed)

---

## 9️⃣ Strings & Numbers

```js
"js".toUpperCase();              // => "JS"
"hello".substr(1,2);             // => "el"
"abc abc".replace("a","A");      // => "Abc abc" (first only)

// Escaping & templates (ES5)
var greet = "Hi, "+user.name+"!";

// Number helpers
(4.567).toFixed(1);              // => "4.6"
parseFloat("3.14px");            // => 3.14
isNaN("NaN");                    // => true
```

---

## 🔟 JSON (Browser & Node built-in)

```js
var txt = '{"a":1,"b":2}';
var obj = JSON.parse(txt);       // => {a:1,b:2}

var out = JSON.stringify(obj);   // => '{"a":1,"b":2}'
```

---

## 1️⃣1️⃣ Date & Time

```js
var now = new Date();            // current
now.getFullYear();               // => 2025
now.getHours();                  // => 11 (local)

var tmr = new Date(now.getTime()+864e5); // +1 day
Date.parse("2025-12-31");        // => millis
```

**Best Practice:** **Store UTC (ISO 8601)**, convert to local only in UI.

---

## 1️⃣2️⃣ Math & Random

```js
Math.max(1,9,2);                 // => 9
Math.min.apply(null,[5,7,1]);    // => 1 (spread alt)
Math.round(4.6);                 // => 5
Math.random();                   // => 0‒0.999...

// Random int helper
function randInt(min,max){ return Math.floor(Math.random()*(max-min+1))+min; }
randInt(1,6);                    // => 1-6 (dice)
```

---

## 1️⃣3️⃣ Browser Essentials

```js
// DOM Select
var el = document.getElementById("title");
document.querySelector(".cls");

// Manipulate
el.textContent = "New";          // safe (no HTML injection)
el.className += " active";       // add class

// Events
document.getElementById("btn").addEventListener("click", handler);
function handler(e){ console.log("Clicked", e.target); }

// Event delegation (single listener for many)
document.getElementById("list").onclick = function(e){
  if (e.target.nodeName === "LI") alert(e.target.textContent);
};

// Storage
localStorage.setItem("key","123");
localStorage.getItem("key");     // => "123"
```

**Best Practice:** Use **event delegation** for dynamic lists; always remove listeners if not needed.

---

## 1️⃣4️⃣ Timers & Async

```js
var id = setTimeout(function(){ console.log("1s"); },1000);
// clearTimeout(id);

var tick = setInterval(function(){ console.log("tick"); },1000);
// clearInterval(tick);
```

---

## 1️⃣5️⃣ Error Handling

```js
try {
  JSON.parse("bad");             // throws
} catch (e) {
  console.error("Parse failed:", e.message);
} finally {
  console.log("Always runs");
}
throw new Error("Fatal!");        // custom error
```

**Best Practice:** **Fail fast** – throw early, catch high-level.

---

### 1️⃣6️⃣ Common **Shorthands vs Full Forms** (with inline results)

| Intent                | Full Code (ES5-friendly)                    | Shorthand (⚡)                     | Example ↔ Result                      |
| --------------------- | ------------------------------------------- | --------------------------------- | ------------------------------------- |
| **Default value**     | `var val = (arg !== undefined) ? arg : 10;` | \`var val = arg10;\`              |  `arg = 5 → val = 5`<br>`arg = undefined → val = 10`|
| **Swap variables**    | `var t = a; a = b; b = t;`                  | `[a, b] = [b, a];` <br>*ES6 only* | `a = 1, b = 2 → a = 2, b = 1`         | 
| **Convert to number** | `Number(str);`                              | `+str;`                           | `str = "42" → 42`                     |
| **Boolean cast**      | `Boolean(x);`                               | `!!x;`                            | `x = "" → false`<br>`x = "hi" → true` |

> *Use the ES6 swap shorthand only when ES6 syntax is allowed; stick to the full form in strict ES5 environments.*


---

### 🔑 Golden Rules Recap

1. **Strict equality (`===`)** – avoid implicit coercion bugs.
2. **Minimize globals** – wrap code in IIFEs or modules.
3. **Use `.forEach` / higher-order methods** for clarity; fall back to classic loops only when profiling says so.
4. **Never trust user input** – always validate & escape before DOM/HTML insertion.
5. **Document your functions** – name them & describe expected types / returns.

---
