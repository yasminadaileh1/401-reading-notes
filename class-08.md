# Express Routing & Connected API :twisted_rightwards_arrows:

## Routing :car:

**Routing** refers to how an application’s **endpoints** (URIs) **respond** to client requests.
We can define routing using **methods of the Express app** object that correspond to HTTP methods like `GET requests` , `POST requests` also use `app.all()` to handle **all HTTP methods** and `app.use()` to **specify middleware** as the callback function.

These routing methods specify a **callback function** called when the application receives a request to the specified route `(endpoint)` and HTTP method, the application `“listens”` for requests that match the specified route(s) and method(s).

The following code is an **example** of a **basic route**:

```
var express = require('express')
var app = express()

// respond with "hello world" when a GET request is made to the homepage
app.get('/', function (req, res) {
  res.send('hello world')
})
```

**Example** of routes that are defined for the **GET and the POST methods** to the root of the app:

```
// GET method route
app.get('/', function (req, res) {
  res.send('GET request to the homepage')
})

// POST method route
app.post('/', function (req, res) {
  res.send('POST request to the homepage')
})
```

### Route Paths :beginner:

**Route paths**, in **combination with a request method**, define the endpoints at which requests can be made. Route paths can be `strings`, `string patterns`, or `regular expressions`.

### Route Parameters :triangular_ruler:

**Route parameters** are named URL segments that are used to **capture the values position in the URL**. The captured values are populated in the req.**Params object**, with the **name of the route** parameter specified in the path as their respective keys.

`Route path: /users/:userId/books/:bookId`
`Request URL: http://localhost:3000/users/34/books/8989`
`req.params: { "userId": "34", "bookId": "8989" }`

### Route Handlers :muscle:

You can provide **multiple callback** functions that **behave like middleware** to handle a request. The only exception is that these callbacks **might invoke next`('route')` to bypass the remaining route callbacks**.

### Response Methods :speech_balloon:

| Method           | Description                                                                           |
| ---------------- | ------------------------------------------------------------------------------------- |
| res.download()   | Prompt a file to be downloaded.                                                       |
| res.end()        | End the response process.                                                             |
| res.json()       | Send a JSON response.                                                                 |
| res.jsonp()      | Send a JSON response with JSONP support.                                              |
| res.redirect()   | Redirect a request.                                                                   |
| res.render()     | Render a view template.                                                               |
| res.send()       | Send a response of various types.                                                     |
| res.sendFile()   | Send a file as an octet stream.                                                       |
| res.sendStatus() | Set the response status code and send its string representation as the response body. |


## Learn to Use the New Router in ExpressJS 4.0
**Express 4.0** comes with the new `Router`. Router is like a mini express application. It doesn't bring in views or settings, but provides us with the routing APIs like `.use`, `.get`, `.param`, and `route`.
We will house our routes in the `server.js` file. In the future it will want to move these out into their own files to keep our application modular. Start up the Node application need `package.json` file to define our dependencies.


**Bookmark / Skim** :star:

- [using express routing;](https://expressjs.com/en/guide/routing.html)
- [express routing](https://scotch.io/tutorials/learn-to-use-the-new-router-in-expressjs-4)

