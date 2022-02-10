# Web Storage API

- In JavaScript, data is stored as a string
- In JavaScript, each character takes up 2 bytes of space

## Local storage

- Local storage saved to the browser until you removed
- Local Storage is shared on the tabs of a single domain in the browser
- Store 10 MB per resource | 5 MB -> 5 mega character -> 5 Million character
- Data is not sent to the server -> The server could not access the CURD data
- You can use 'storage event'

```js
// ========== Set item ==========
localStorage.setItem('name', 'Masoud Karimi');
localStorage.name = 'Masoud Karimi';
localStorage['name'] = 'Masoud Karimi'

// ========== Get item ==========
console.log(localStorage.getItem('name')) // Masoud Karimi
console.log(localStorage.name) // Masoud Karimi
console.log(localStorage['name']) // Masoud Karimi

// ========== Remove item ========== 
localStorage.removeItem('name')

// ========== Clear all items ========== 
localStorage.clear()

// ========== Key ========== 
console.log(localStorage.key(0)) // name

// ========== Example ==========
let colors = ['red', 'green', 'blue']
localStorage.setItem('colors', colors)
console.log(localStorage.getItem('colors')) // Return string => red,green,blue

// This is true way
let colors = ['red', 'green', 'blue'];
localStorage.setItem('colors', JSON.stringify(colors))
console.log(localStorage.getItem('colors')); // Return string => red,green,blue
console.log(JSON.parse(localStorage.getItem('colors'))); // Return Array => ['red', 'green', 'blue']
```

## Session storage

- The Session storage is saved in the browser until the tab or browser is closed
- Store 10 MB per resource | 5 MB -> 5 mega character -> 5 Million character
- Data is not sent to the server -> The server could not access the CURD data
- You can use 'storage event'

```js
// ========== Set item ==========
sessionStorage.setItem('name', 'John Doe')
sessionStorage.name = 'John Doe';
sessionStorage['name'] = 'John Doe'

// ========== Get item ==========
console.log(sessionStorage.getItem('name'))
console.log(sessionStorage.name)
console.log(sessionStorage['name'])

// ========== Remove item ==========
sessionStorage.removeItem('name')

// ========== Clear all items ==========
sessionStorage.clear()

// ========== Key ==========
console.log(sessionStorage.key(0))

// ========== Example ==========
let colors = ['red', 'green', 'blue']
sessionStorage.setItem('colors', colors)
console.log(sessionStorage.getItem('colors'))

// This is true way
let colors = ['red', 'green', 'blue']
sessionStorage.setItem('colors', JSON.stringify(colors))
console.log(sessionStorage.getItem('colors')) // Return string
console.log(JSON.parse(sessionStorage.getItem('colors'))) // Return Array 
```
