# Javascript OOP (Object-Oriented Programming)


## Class (Syntactic Sugar)
```js
class User {
    constructor(email, name) {
        this.email = email
        this.name = name
        this.score = 0
    }

    login() {
        console.log(`${this.email} just logged in`)
        return this // For Chaining
    }

    logout() {
        console.log(`${this.email} just logged out`)
        return this // For Chaining
    }

    updateScore() {
        this.score++
        console.log(`${this.email} score is now ${this.score}`)
        return this // For Chaining
    }
}

let userOne = new User('masoud@gmail.com', 'Masoud')
let userTwo = new User('mahdi@gmail.com', 'Mahdi')
console.log(userOne, userTwo)


// =============== Chaining ===============
userOne.login().updateScore().updateScore().logout()


// =============== Inheritance ===============
class Admin extends User {
    deleteUser(user) {
        users = users.filter(item => item.email !== user.email)
    }
}

let admin = new Admin('reza@gmail.com', 'Reza')
let users = [userOne, userTwo, admin]
admin.deleteUser(userTwo)
console.log(users)
```

## Create Class with Function
```js
function User(email, name) {
    this.email = email
    this.name = name
    this.status = false
}

// =============== Prototype ===============
User.prototype.login = function () {
    this.online = true
    console.log(`${this.email} just logged in`)
}
User.prototype.logout = function () {
    this.online = false
    console.log(`${this.email} just logged out`)
}

let userOne = new User('masoud@gmail.com', 'Masoud')
let userTwo = new User('mahdi@gmail.com', 'Mahdi')
console.log(userOne)
userOne.login()
userTwo.logout()

// =============== Prototype Inheritance ===============
function Admin(...args) {
    User.apply(this, args)
    this.role = 'super admin'
}

Admin.prototype = Object.create(User.prototype)
Admin.prototype.deleteUser = function (user) {
    users = users.filter(item => item.email !== user.email)
}

let admin = new Admin('reza@gmail.com', 'Reza')
let users = [userOne, userTwo, admin]
console.log(admin)
admin.login()
admin.deleteUser(userTwo)
console.log(users)
```