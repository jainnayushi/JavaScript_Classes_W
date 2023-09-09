# History

- 1995 -> Netscape Navigator browser
- `Brendan Eich` -> 10 days -> Named Mocha -> LiveScript -> JavaScript (publicity)
- 1996 -> Internet Explorer -> old + new features -> JScript
- Problem -> Website works well in either of the browser -> best viewed
- ECMA (standarizes lang) -> Named ECMAScript
- ES1 - 1997
  ES2
  ....
  ES6 - 2015
- TC39 (Technical Community 39) now decides JS Release
---

# Strict Mode

- Is a way to opt in to a restricted variant of JS. `Use it to avoid mistakes`.
- There are some things like ;, which JS ignores but should be taken care by programmer so use this mode. It will remind of such mistakes
- The "use strict" directive was `new in ECMAScript version 5`. It is not a statement, but a literal expression, ignored by earlier versions of JavaScript.
- Strict mode makes it easier to write "secure" JavaScript, changes previously accepted "bad syntax" into real errors.
- In strict mode, any assignment to a non-writable property, a getter-only property, a non-existing property, a non-existing variable, or a non-existing object, will throw an error.

```js
"use strict";
let x;
```

---

# Naming Variables

- letters + $ + \_ + number
- Can't start with number
- Can use underscore or `dollar $` symbol
- Can't use spaces
  first_name - Snake Case,
  firstName - Camel Case (convention)

---

# Let vs Const vs Var

- let

1. Simple initialization
2. Simple declaration
3. `Can't be redeclared`
4. Can be reinitialized

- const

1. Initialization is must with declaration
2. `Can't be redeclared`
3. `Can't be reinitialized`

- var

1. Everything is simple
  
---

- Initilization - Declaration - Redeclaration - Reinitialization

```js
1101;
let firstName;
let firstName = "ashi";
let firstName = "ayushi";
Error; // can't declare again
firstName = "jain"; // can reinitialize
```

```js
1*1*00
const firstName; Error // can't just declare, have to initialize
const firstName = "ashi";
const firstName = "ayushi"; Error // can't declare again
firstName = "jain"; Error // can't reinitialize
```

```js
1111;
var firstName;
var firstName = "ashi";
var firstName = "ayushi"; // can declare again
firstName = "jain"; // can reinitialize
```

---

# String

- Indexing
- Length
- Common Methods - trim(), toUpperCase(), toLowerCase(), slice()

```js
let firstName = "ayushi";
console.log(firstName[0]); /// a
console.log(firstName.length); /// 6

console.log(firstName[firstName.length - 2]); /// h // Indexing + length
firstName = firstName.trim(); ///"ayushi" //"  ayushi  " len=10 -> "ayushi" len=6
firstName = firstName.toUpperCase(); ///AYUSHI
firstName = firstName.toLowerCase(); ///ayushi
let newString = firstName.slice(1, 4); /// yu // [1,4)
```

---

# Data Types (Primitive)

- string
- number
- booleans
- undefined
- null
- BigInt
- Symbol

# Falsy Values

- False, "", null, undefined, 0

---

# typeof Operator

- `Bug in Javascript` typeof Null = Object

```js
let myVariable = null;
console.log(typeof myVariable); /// Object //exception
```

For rest primitive datatypes its same as type

# BigInt

```js
console.log(Number.MAX_SAFE_INTEGER); /// 9007199254740991 // largest int
// Creating BigInt
// 1
let x = BigInt(2); //it can be a very small number
// 2
let y = 3n;
//Operations
console.log(x + y); ///5n
```

---

# Conversion Trick

Convert String to Number

```js
// 1
let age = +"18";
console.log(typeof myStr); ///Number //18
// 2
age = Number(age);
console.log(typeof age); ///Number //18
```

Convert Number to String

```js
// 1
let age = 22;
age = age + "";
console.log(typeof age); ///String //"22"
// 2
age = String(age);
console.log(typeof age); ///String
```

---

# null vs undefined

- null is a variable that is `defined` but is `missing a value`.
  undefined is a variable that refers to something that `doesn't exist`, and the variable `isn't defined` to be anything.
- null - can be initialized later
  undefined - has not been initialized
- undefined == null ///true
  undefined === null ///false // type is different

```js
let firstName;
console.log(typeof firstName); /// undefined
firstName = "Ayushi";
console.log(typeof firstName, firstName); /// String Ayushi

let myVariable = null;
console.log(myVariable); ///null
myVariable = "Ayushi";
console.log(typeof myVariable, myVariable); /// String Ayushi
console.log(typeof null); /// Object //exception
```

---

# Switch Statement

```js
let day = 9;

switch (day) {
  case 0:
    console.log("Sunday");
    break;
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  default:
    console.log("Invalid Day");
}
```

---

# Break and Continue

- Break - Comes out of the inner loop - Terminates
- Continue - `Goes to next iteration -> incremental vali step par` - Skips

```js
for (let i = 1; i <= 10; i++) {
  if (i === 4) {
    break;
  }
  console.log(i);
} /// 1 2 3

for (let i = 1; i <= 10; i++) {
  if (i === 4) {
    continue;
  }
  console.log(i);
} /// 1 2 3 5 6 7 8 9 10
```

---

# For , While, Do - While Loop

```js
// for
for (let i = 0; i <= 9; i++) {
  console.log(i);
} /// 0 1 2 3 4 5 6 7 8 9

// while
let i = 0;
while (i <= 9) {
  console.log(i);
  i++;
} /// 0 1 2 3 4 5 6 7 8 9

// do while
let i = 10;
do {
  console.log(i); /// 10
  i++;
} while (i <= 9);
console.log("value of i is ", i); /// 11
```

---