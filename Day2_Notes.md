# Array

```js
let mixed = [1, 2, 2.3, "string", null, undefined];
// Type of
console.log(typeof mixed); /// Object
// Check if its really array
console.log(Array.isArray(mixed)); ///True
// Indexing
console.log(mixed[1]); ///2
```

- `Values inside const array can be changed`
- Value of const primitive type can not be changed - address is not changed

```js
const pi = 3.14;
pi = 3; /// Error //address changed
const mixed = [1, 2, 2.3, "string", null, undefined];
mixed[1] = "hey";
console.log(mixed); /// [1,"hey",2.3, "string", null, undefined] // Adress didn't change
const mixed = ["a", "b"]; /// Error // Address got changed
```

---

# Array Insert- Delete Operations

### Can change original array

- Push - Inserts element at the end
- Pop - Removes element from the end and `also returns it`
- Unshift - Inserts element at the beginning
- Shift - Removes element from the beginning and `also returns it`

### Push - Pop are faster than Shift-Unshift

- (Coz in shift unshift, all the array elements have to be shifted for addition/removal in the starting so rearrangement of elements take time)

---

```js
let fruits = ["apple", "mango", "grapes"];
```

```js
// push
fruits.push("banana");
console.log(fruits); /// ["apple", "mango", "grapes", "banana"]
```

```js
// pop
let poppedFruit = fruits.pop(); // returns too
console.log(fruits); ///["apple", "mango"]
console.log("popped fruit is", poppedFruit); /// Popped fruit is grapes
```

```js
// unshift
fruits.unshift("banana");
fruits.unshift("myfruit");
console.log(fruits); /// ["myfruit","banana","apple", "mango", "grapes" ]
```

```js
// shift
let removedFruit = fruits.shift(); // returns too
console.log(fruits); /// ["mango", "grapes"];
console.log("removed fruits is ", removedFruit); /// Removed fruit is apple
```

---

# Primitive vs Reference data types

```js
// Primitive type - number -> Stack -> Different memory location -> Values are independent
let num1 = 6;
let num2 = num1;
console.log("value is num1 is", num1); /// 6
console.log("value is num2 is", num2); /// 6
num1++;
console.log("after incrementing num1");
console.log("value is num1 is", num1); /// 7
console.log("value is num2 is", num2); /// 6
```

```js
// Reference type - array -> Heap -> Share same adress -> Values are dependent
let array1 = ["item1", "item2"];
let array2 = array1;
console.log("array1", array1); /// ["item1", "item2"]
console.log("array2", array2); /// ["item1", "item2"]
array1.push("item3");
console.log("after pushing element to array 1");
console.log("array1", array1); /// ["item1", "item2", "item3"]
console.log("array2", array2); /// ["item1", "item2", "item3"]
```

---

# Cloning array

- 1 - Copying - Not correct for large arrays
  let array2 = ["item1", "item2"];
- 2 - Slicing
  let array2 = array1.slice(0);
- 3 - Concatenation
  let array2 = [].concat(array1);
- 4- Spread Operator
  let array2 = [...array1];

```js
// 1 - Copying - Not correct for large arrays
let array1 = ["item1", "item2"];
let array2 = ["item1", "item2"];
array1.push("item3");
console.log(array1 === array2); /// False
```

---

```js
// 2 - Slicing
let array1 = ["item1", "item2"];
let array2 = array1.slice(0);
array1.push("item3");
console.log(array1 === array2); /// False
```

```js
// 3 - Concatenation
let array1 = ["item1", "item2"];
let array2 = [].concat(array1); // array1.concat(array2)
array1.push("item3");
console.log(array1 === array2); /// False
```

```js
// 4- Spread Operator
let array1 = ["item1", "item2"];
let array2 = [...array1];
array1.push("item3");
console.log(array1 === array2); /// False
```

---

# Concatenaton

array 1 + "item3" + "item4"

```js
let array1 = ["item1", "item2"];
// 1 - Slicing + Concatenation
let array2 = array1.slice(0).concat(["item3", "item4"]);
// 2 - Concatenation
let array2 = [].concat(array1, ["item3", "item4"]);
// 3 - Spread Operator
let array2 = [...array1, "item3", "item4"];
// ...arr = elements of arr => a,b,c
// arr = array => [a,b,c]
```

---

# Array Destructuring

```js
const myArray = ["value1", "value2", "value3", "value4"];


// 1 - Getting 2 values
let [myvar1, myvar2] = myArray;
console.log("value of myvar1", myvar1); /// value1
console.log("value of myvar2", myvar2); /// value2

// 2 - Getting 2 values and rest in other variable
let [myvar1, myvar2, ...myNewArray] = myArray;
console.log("value of myvar1", myvar1); /// value1
console.log("value of myvar2", myvar2); /// value2
console.log(myNewArray); /// [ "value3","value4"]

// 3 - Skipping values
let [myvar1, , myvar3] = myArray;
console.log("value of myvar1", myvar1); /// value1
console.log("value of myvar3", myvar3); /// value3

// 4 - Destructing values more than array contains
const myArray = ["value1"];
let [myvar1, myvar2, myvar3] = myArray;
console.log("value of myvar1", myvar1); /// value1
console.log("value of myvar2", myvar2); // Undefined
console.log("value of myvar3", myvar3); // Undefined
```

---

# Loop in Array

```js
let fruits = ["apple", "mango", "grapes"];

// 1 - Normal loop
let fruits2 = [];
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]); /// each element
  fruits2.push(fruits[i].toUpperCase());
}
console.log(fruits2); /// ["APPLE", "MANGO", "GRAPES"]
```

```js
// 2 - While loop
const fruits2 = [];
let i = 0;
while (i < fruits.length) {
  fruits2.push(fruits[i].toUpperCase());
  i++;
}
console.log(fruits2); /// ["APPLE", "MANGO", "GRAPES"]
```

---

# 3 - for of loop - Element

```js
for (let fruit of fruits) {
  console.log(fruit);
}
/// apple mango grapes
```

# 4 - for in loop - Index

```js
for (let index in fruits) {
  console.log(index);
  console.log(fruits[index]);
}
/// 0 1 2
/// apple mango grapes
```

---

# Array Methods

### forEach Method : `array.forEach(callback function)`

- Calls callback function for each of its element
- Default params of callback are `(element, its index)` - index is in our hand we want to use/not

```js
const num = [4, 2, 5, 8];
function myFunc(number, index) {
  console.log(`index is ${index} number is ${number}`);
}
// 1 - Using for loop
for (let i = 0; i < num.length; i++) {
  myFunc(num[i], i);
}
// 2 - Using forEach()
num.forEach(myFunc);
// 3 - Using forEach() - anonymous callback
num.forEach(function (number, index) {
  console.log(`index is ${index} number is ${number}`);
});
```

---

# Practical example of forEach

```js
const users = [
    {firstName: "ayushi", age: 23},
    {firstName: "ishu", age: 21},
    {firstName: "yash", age: 22},
    {firstName: "krish", age: 20},
]
// For of loop
for(let user of users){
    console.log(user.firstName);
}
// forEach()
users.forEach(function(user) {
    console.log(user.firstName);
});
// or 
users.forEach((user) =>{
    console.log(user.firstName);
});
// or
users.forEach(user =>console.log(user.firstName););
```

---
