# Web Storage API

- In JavaScript, data is stored as a string
- In JavaScript, each character takes up 2 bytes of space

# Table of contents

- [Local storage](#local-storage)
- [Session storage](#session-storage)
- [Storage event](#storage-event)
- [IndexDB](#indexeddb)

## Local storage

- Local storage saved to the browser until you removed
- Local Storage is shared on the tabs of a single domain in the browser
- Store 10 MB per resource | 5 MB -> 5 mega character -> 5 Million character
- Data is not sent to the server -> The server could not access the CURD data
- You can use 'storage event'

```js
// ========== Set item ==========
localStorage.setItem('name', 'Masoud Karimi')
localStorage.name = 'Masoud Karimi'
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
let colors = ['red', 'green', 'blue']
localStorage.setItem('colors', JSON.stringify(colors))
console.log(localStorage.getItem('colors')) // Return string => red,green,blue
console.log(JSON.parse(localStorage.getItem('colors'))) // Return Array => ['red', 'green', 'blue']
```

**[⬆ back to top](#table-of-contents)**

## Session storage

- The Session storage is saved in the browser until the tab or browser is closed
- Store 10 MB per resource | 5 MB -> 5 mega character -> 5 Million character
- Data is not sent to the server -> The server could not access the CURD data
- You can use 'storage event'

```js
// ========== Set item ==========
sessionStorage.setItem('name', 'John Doe')
sessionStorage.name = 'John Doe'
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

**[⬆ back to top](#table-of-contents)**

## Cookie

- Cookie saved to the browser until you removed
- In each request, cookies are sent to the server
- The server and client have access to the cookie -> The server can access CURD data
- Store 4 KB per resource

```js
// ========== Show all cookies ==========
console.log(document.cookie) // Return all cookies


// ========== Set cookie ==========
const setCookie = ({name, value, days, path}) => {
    let date = new Date()
    date.setTime(date.getTime() + (days * 24 * 60 * 60 + 1000)) // 1 day
    let expires = `expires=${date.toUTCString()}`
    let cookiePath = `path=${path}`

    document.cookie = `${name}=${value}; ${expires}; ${cookiePath};`
}

setCookie({name: 'name', value: 'Masoud', days: 1, path: '/'})
setCookie({name: 'family', value: 'Karimi', days: 1, path: '/'})


// ========== Get cookie ==========
const getCookie = ({name}) => {
    let cookieName = `${name}=`
    let cookies = document.cookie.split(';')

    for (let i = 0; i < cookies.length; i++) {
        let cookie = cookies[i]

        while (cookie.charAt(0) == ' ') {
            cookie = cookie.substring(1)
        }

        if (cookie.indexOf(cookieName) == 0) {
            return cookie.substring(cookieName.length, cookie.length)
        }
    }
    return ''
}

getCookie({name: 'name'}) // Return 'Masoud'
getCookie({name: 'family'}) // Return 'Karimi'


// ========== Check cookie ==========
const checkCookie = ({name}) => {
    let cookie = getCookie({name})

    if (cookie != '') {
        return true
    } else {
        return false
    }
}

checkCookie({name: 'name'}) // Return true
checkCookie({name: 'family'}) // Return true


// ========== Delete cookie ==========
const deleteCookie = ({name}) => {
    let cookieValue = getCookie({name})

    if (cookieValue != '') {
        let date = new Date()
        date.setTime(date.getTime() - (24 * 60 * 60 + 1000)) // 1 day
        let expires = `expires=${date.toUTCString()}`
        let path = `path=/`

        document.cookie = `${name}=${cookieValue}; ${expires}; ${path};`
    }
}

deleteCookie({name: 'name'})
deleteCookie({name: 'family'})
```

**[⬆ back to top](#table-of-contents)**

## Storage Event

- Any change we make to local storage will call the storage event to all tabs in that domain except the current tab in
  the browser
- The Storage event is used to synchronize status on different tabs

```js
localStorage.setItem('colors', ['red', 'green', 'blue'])
window.addEventListener('storage', (e) => {
    console.log(
        `The value for ${e.key} was changed from ${e.oldValue} to ${
            e.newValue
        } in ${e.url} and ${JSON.stringify(e.storageArea)}`
    )
})

// or

window.onstorage = (e) => {
    console.log(
        `The value for ${e.key} was changed from ${e.oldValue} to ${
            e.newValue
        } in ${e.url} and ${JSON.stringify(e.storageArea)}`
    )
}
```

**[⬆ back to top](#table-of-contents)**

## IndexedDB

- Like NoSQL database