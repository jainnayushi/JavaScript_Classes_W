# Sort()

- `Changes original array`
- `Sorts everything thinking as array`
- `Capital letters sorts first then small letters`
- Solution :- array.sort(callback(a, b) { return a-b/ b-a} )
- Descending : b-a, Ascending : a-b

### ASCII Values

- char : ascii value
- '0' : 48..........'9' : 57
- 'A' : 65..........'Z' : 90
- 'a' : 97..........'z' : 122

---

- Problem

```js
const num = [5, 9, 1210, 410, 3000]; // -> ["5", "9", "1210", "410", "3000"];//interpret as string
num.sort();
console.log(num); /// [1210, 3000, 410, 5, 9]
// Working 1 -> 3 -> 4 -> 5 -> 9 and  5, 9, 410, 1200, 3000 (expected)

// ASCII Code : A - 47, a - 96
// Sorts capital first
const userNames = [
  "harshit",
  "abcd",
  "mohit",
  "nitish",
  "aabc",
  "ABC",
  "Harshit",
];
userNames.sort();
console.log(userNames); //[ABC, Harshit, aabc, abcd, harshit, mohit, nitish]
```

- Solution

```js
const numbers = [5, 9, 1200, 410, 3000];
numbers.sort((a, b) => {return b - a;});
// numbers.sort((a,b)=>a-b);
console.log(numbers); /// [5, 9, 400, 1200, 3000]
// Working - ex : 1200,410 ->  a-b ---> 790
// a-b ---> postive (greater than 0) ---> b, a => 410 , 1200 => order change
// 5, 9 ---> -4
// a-b ---> negative ----> a,b => 5, 9 => order same
```

---

# Practical example of sort()

```js
// Sort price High to Low or vice-versa
const products = [
  { productId: 1, produceName: "p1", price: 300 },
  { productId: 2, produceName: "p2", price: 3000 },
  { productId: 3, produceName: "p3", price: 200 },
  { productId: 4, produceName: "p4", price: 8000 },
  { productId: 5, produceName: "p5", price: 500 },
];
// lowToHigh
const lowToHigh = products.slice(0).sort((a, b) => {
  // using slice(0) to clone new array
  return a.price - b.price;
});
// highToLow
const highToLow = products.slice(0).sort((a, b) => {
  return b.price - a.price;
});

// Example 2
const users = [
  { firstName: "harshit", age: 23 },
  { firstName: "mohit", age: 21 },
  { firstName: "nitish", age: 22 },
  { firstName: "garima", age: 20 },
];
users.sort((a, b) => {
  if (a.firstName > b.firstName) {
    return 1;
  } else {
    return -1;
  }
});
console.log(users);
```

---

# Find()

- Callback func iterates for every element
- `arr.find(callback{return...})`
- `Returns first occurence`

```js
const myArray = ["Hello", "cat", "dog", "lion"];
// Callback func alag se
function isLength3(string) {
  return string.length === 3;
}
const ans = myArray.find(isLength3);
or;
const ans = myArray.find((string) => {
  return string.length === 3;
});
console.log(ans); ///cat
```

---

# Practical example of find()

```js
const users = [
  { userId: 1, userName: "harshit" },
  { userId: 2, userName: "harsh" },
  { userId: 3, userName: "nitish" },
  { userId: 4, userName: "mohit" },
  { userId: 5, userName: "aaditya" },
];

const myUser = users.find((user) => user.userId === 3);
console.log(myUser); /// {userId : 3, userName: "nitish"}
```

---

# every()

- Callback `returns true/false`
- Every() returns true/false -> true if all elements follow callback condition
  -> callback should be true for every element -> then every will return true

```js
const numbers = [2,4,6,8,10];
const ans = numbers.every((number)=>number%2===0);
console.log(ans); /// True

# Practical example
const userCart = [
    {productId: 1, productName: "mobile", price: 12000},
    {productId: 2, productName: "laptop", price: 22000},
    {productId: 3, productName: "tv", price: 35000},
]
const ans = userCart.every((cartItem)=>cartItem.price < 30000);
console.log(ans); /// False
```

---

# Some()

- Callback `returns true/false`
- some() returns true/false -> true if any one elements follow callback condition
- if atleast one follows callback condition

```js
const numbers = [3,5,11,9];
const ans = numbers.some((number)=>number%2===0);
console.log(ans); // False

const userCart = [
    {productId: 1, productName: "mobile", price: 12000},
    {productId: 2, productName: "laptop", price: 22000},
    {productId: 3, productName: "tv", price: 35000},
    {productId: 3, productName: "macbook", price: 250000},
]
const ans = userCart.some((cartItem)=>cartItem.price > 100000);
console.log(ans); /// True
```

---

# fill()
- used to fill array with something
- `arr.fill(value) or (value , start , end(excluding end))`

```js
// 1 - create array of some length, filled with something
const myArray = new Array(10).fill(0); // 10 - length of array, fill with 0
console.log(myArray); ///[0,0,0,0,0,0,0,0,0,0]

// 2 - fill something in between of already made array

const myArray = [1, 2, 3, 4, 5, 6, 7, 8];
myArray.fill(0, 2, 5);
console.log(myArray); ///[1,2,0,0,0,6,7,8]
```

---

# splice()

- `arr.splice(start index , # delete items , insert items)`
- returns array of deleted items
- `Changes original array`

```js
let myArray = ["item1", "item2", "item3"];
// 1 - delete
const deletedItem = myArray.splice(1, 2); //starting with index 1, delete 2 items
console.log("deleted item", deletedItem); ///['item2', 'item3']

// 2 - insert
const insertedItem = myArray.splice(1, 0, "inserted item");
// insert at index 1, insert 'inserted item'
console.log("inserted item", insertedItem); /// [] // since no delete

// 3 - insert and delete
const Item = myArray.splice(1, 2, "inserted item1", "inserted item2");
console.log("item", Item); /// ['item2']

myArray.splice(1, 2, "inserted item1", "inserted item2"); // Changes original array check
console.log(myArray); /// ['item1', 'inserted item1', 'inserted item2']
```

---

# Summary

- forEach() - do something for each element
- map() - returns something for each element - forms new array with returned values
- filter() - returns in T/F - forms new array with elements which returned T
- reduce() - stats - return single value
- find() - returns first occurence
- every() - returns in T/F
- some() - returns in T/F

- sort()
- fill()
- splice()

---

# Iterables

- Jispe hum `for of` loop laga sakein
- `Iterables - string , array, map, sets `
- `object is not iterable`
- ` Array like object - String` - jinke pas length property hoti hai aur jinko hum index se access kar sakte hai

```js
const firstName = "Ayushi";
for (let char of firstName) {
  console.log(char); /// A y u s h i
}
const items = ["item1", "item2", "item3"];
for (let item of items) {
  console.log(item); /// 'item1', 'item2', 'item3'
}
// Array like object - string
const firstName = "ayushi";
console.log(firstName.length); /// 6
console.log(firstName[2]); /// u
```

---
