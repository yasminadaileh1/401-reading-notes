# Authentication :sunglasses:

## User Modeling :busts_in_silhouette:

User models that have sensitive data that should **NEVER** be sent to client applications. If the application requires that users be able to read each others personal information, **create a second Profile model** to hold that data and strictly **limit access** to the Profile model. Safely using a second model will ensure that **no users** will accidentally (or maliciously) **get access to sensitive information**.

## Cryptography :envelope:

**Cryptography** is the science which studies methods for **encoding messages** so that they can be read only by a person who knows the **secret information required for decoding** (key).

## Hash Algorithms :memo:

**Hash Algorithms** produces a hash that is deliberately difficult to reverse and it's often used for checking the integrity of data.

## Cypher Algorithms :arrows_counterclockwise:

A **Cryptographic Cypher Algorithm** takes a piece of **data and a key** and produces encrypted data. Later the **encrypted data** can be reversed into the **original data** by decrypting it using the same key.

## Basic Authorization :hand:

Basic Authorization is a common method used to **send a username and password** in an **HTTP request**. A **Server can decode** the Basic Authorization header to retrieve the username and password.
In browsers, we get `atob` and `btoa` to convert to/from “Base64 Encoding”.
Example:
```
let encoded = window.btoa('someusername:P@55w0rD!')
// c29tZXVzZXJuYW1lOlBANTV3MHJEIQ==

let decoded = window.atob('c29tZXVzZXJuYW1lOlBANTV3MHJEIQ==');
// someusername:P@55w0rD!

request({
  method: 'GET',
  url: 'https://api.example.com/login',
  headers: {
    Authorization: `Basic ${encoded}`,
  },
})
.then(handleLogin)
.catch(handleLoginError)
```
In a node application, we can use a node module to do the same work (those methods are not built-in):
```
let base64 = require('base-64');

let string = 'someusername:P@55w0rD!';
let encoded = base64.encode(string); // c29tZXVzZXJuYW1lOlBANTV3MHJEIQ==
let decoded = base64.decode(encoded); // someusername:P@55w0rD!
```

**Additional Resources** :partly_sunny:

**Bookmark / Skim** :star:

- [securing passwords](http://dustwell.com/how-to-handle-passwords-bcrypt.html)
- [basic auth](https://en.wikipedia.org/wiki/Basic_access_authentication)
- [intro to jwt](https://jwt.io/introduction/)
- [OWASP auth cheatsheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)
- [bcrypt docs](https://www.npmjs.com/package/bcrypt)
