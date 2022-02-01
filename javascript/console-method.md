# Console Method

## Console group and types of display modes

```js
console.groupCollapsed('Group collapsed');
console.group('Group');
console.log('Log');
console.info('Info');
console.warn('Warning');
console.error('Error');
console.groupEnd('Groudp end');
```

## Console clear

```js
console.clear();
```

## Console time

```js
console.time();

function timerLog() {
    setTimeout(() => {
        console.log('Test timer log');
    }, 3000);
}

console.timeLog();
console.timeStamp();
timerLog();
console.timeEnd();
```

## Console table

```js
let table = [
    [1, 2, 3],
    [1, 2, 3],
];
console.table(table);
```

## Console count

```js
for (let i = 0; i <= 10; i++) {
    console.count(i);
}
```

## Console custom style

```js
const spacing = `10px`;
const styles = `padding: ${spacing}; background-color: red;  color: white; border-radius: 10px; margin: 20px 0; 10px; font-size: 15px`;
console.log('%c Hello World!', styles); 
```






















