# unit 2 men stake notes

| CRUD Action | RESTful Action | HTTP Method | Definition |
| ----------- | -------------- | ----------- | ------------------------ |
|  | `new` | `GET` | Show a form to create a new item |
| Create | `create` | `POST` | Add a new item to the database |
| Read | `index` | `GET` | Show all items |
| Read | `show` | `GET` | Show one specific item |
|  | `edit` | `GET` | Show a form to edit an existing item |
| Update | `update` | `PUT` | Save changes to an existing item |
| Delete | `delete` | `DELETE` | Remove an item from the database |


## SETUP 
- creat a directory (mkdir)
- creat server file `touch server.js`
- initialize a node project with `npm init -y`
- install express `npm i express`

### Write Server Boilerplate 

server.js
```js
// to import express packege to our server
const express = require('express')

//to use express
const app = express()




app.listen(3000, function () {
    console.log('Listening on port 3000')
})
```

Run server with `nodemon server.js` or only `nodemon`

Use `ctrl + c` to stop the server from the terminal.

Navigat to `http://localhost:3000/` to view our server 

To print in the server 
```
app.get('/', (req, res) => {
    res.send('<h1>hello world 😜</h1>')
})
```
