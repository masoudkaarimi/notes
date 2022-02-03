# Custom Event

```html
<h1 id="number">0</h1>
<button id="increaseBtn">increase</button>
<button id="decreaseBtn">Decrease</button>
```

```js
const numberElement = document.getElementById('number');
const increaseBtn = document.getElementById('increaseBtn');
const decreaseBtn = document.getElementById('decreaseBtn');
let number = 0;

console.log(numberElement);
console.log(increaseBtn);
console.log(decreaseBtn);


increaseBtn.addEventListener('click', () => {
    number++;

    numberElement.dispatchEvent(
        new CustomEvent('number change :)', {
            // cancelable: false, // e.preventDefault() Will Not Work
            detail: {
                number,
            },
        })
    );
});

decreaseBtn.addEventListener('click', () => {
    number--;

    numberElement.dispatchEvent(
        new CustomEvent('number change :)', {
            // cancelable: false, // e.preventDefault() Will Not Work
            detail: {
                number,
            },
        })
    );
});

numberElement.addEventListener('number change :)', (event) => {
    console.log(event);

    event.currentTarget.innerHTML = event.detail.number;
});
```