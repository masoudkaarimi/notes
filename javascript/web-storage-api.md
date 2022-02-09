# Web Storage API

## Local storage

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
