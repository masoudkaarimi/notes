# ECMAScript 2015 (ES6)

## Spread operator (...)

```js
// =============== https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax ===============
let array = ['a1', 'a2', 'a3']
console.log(array)
console.log(...array)



const addNums = (a, b, c) => {
    return a + b + c
}
let nums = [1, 2, 3]
console.log(addNums(nums)) // error -> 1,2,3undefinedundefined
console.log(addNums(...nums)) // 6



let params = ['hello', true, 7]
let other = [1, 2, ...params] // [ 1, 2, "hello", true, 7 ]

const myFunction = (x, y, ...a) => {
    return (x + y) * a.length
}
myFunction(1, 2, ...params)



let str = 'Masoud'
let chars = [...str] // ["M", "a", "s", "o", "u", "d"]
console.log(chars)



let parts = ['two', 'three']
let numbers = ['one', ...parts, 'four']
console.log(numbers)



const sum = (a, b, c) => {
    return a + b + c
}
let args = [1, 2, 3]
console.log(...args)
console.log(sum(...args))



const tag = (strings, ...values) => {
    console.log(strings[0]);
    console.log(strings[1]);

    console.log(values[0]);
    console.log(values[1]);
}
tag`Hello ${2 + 2} world ${3 * 3}`



// Rest parameters
// https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters
const sum = (...numbers) => {
    // or
    // let numbers = Array.prototype.slice.call(arguments);
    let result = 0
    numbers.forEach((number) => (result += number))
    return result
}
console.log(sum(1, 2))
console.log(sum(1, 2, 3, 4))

```