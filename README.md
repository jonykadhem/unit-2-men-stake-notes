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
- creat a `.gitignore`
- initialize a node project with `npm init -y`
- install express and morgan `npm i express morgan`

### Add `node_modules` to `.gitignore`
.gitignore
```bash
node_modules
```

### Write Server Boilerplate 

server.js
```js
// to import express packege and morgan to our server
const express = require('express')
const morgan = require('morgan')

//to use express & morgan
const app = express()
app.use(morgan('dev'))




app.listen(3000, function () {
    console.log('Listening on port 3000')
})
```

Run server with `nodemon server.js` or only `nodemon`

Use `ctrl + c` to stop the server from the terminal.

Navigat to `http://localhost:3000/` to view our server 

### creating a test rout
To print in the server 
```js
app.get('/', (req, res) => {
    res.send('<h1>hello world 😜</h1>')
})
```
changing the path

```js
app.get('/home', (req, res) => {
    res.send('<h1>Home page</h1>')
    // console.log(req)
})
app.get('/test', (req, res) => {
    res.send('<button>responds with text</button>')
    // console.log(req)
})
```

Navigat to `http://localhost:3000/home` or `/test` to view our server 

### using request parameters 

```js
app.get('/greet/:name', (req, res) => {
    res.send(`<h1>Hello : ${req.params.name}</h1>`)
    console.log(req.params)
    // console.log(req)
})
```

Navigat to `http://localhost:3000/greet/mohsen` to view our server 


### using request query 
```js
//http://localhost:3000/hello/?name=mohsen&age=26
app.get('/hello', (req,res) => {
    const name = req.query.name
    const age = req.query.age
    res.send(`hello world ${req.query.name} ${req.query.age}`)
    console.log(req.query)
})
```
### this code is how to render an `Ejs`
- first inistall `ejs` by `npm i ejs`
- creat `views` directory
- creat `fileName.ejs` file
- add HTML boilerplate with `!`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Home</title>
</head>
<body>
    <h1>HELLO POTATOS 🥔</h1>
</body>
</html>
```
- write a render code in the server Ex:
 ```js
app.get('/', (req, res) => {
  res.render('fileName.ejs')
});
 ```

### ejs syntax

to use JS in ejs file use `<% %>`
```ejs
<% if(showMessage === false){ %>
```

to display JS content use `<%= %>`
```ejs
 <p>Good Number Is <%= favoriteNumber %></p>
```
