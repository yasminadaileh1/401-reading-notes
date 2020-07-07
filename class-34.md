# Authentication / Role Based Authorization :closed_lock_with_key:

## role-based access control (RBAC) :key:
**Role-based access control (RBAC)** restricts network access based on a person's role within an organization one of the main methods for advanced access control. The roles in RBAC refer to the **levels of access** that employees have to the **network**.

**BENEFITS OF RBAC:**
1. Reducing administrative work and IT support.
1. Maximizing operational efficiency.
1. Improving compliance.



## React Cookies :cookie:
**Load** and **save** cookies with React.

To install it:
`$ npm install react-cookies --save`

To be able to **access user cookies** while doing server-rendering, you can use `plugToRequest` or `setRawCookie`.

#### API :paw_prints:
`.load(name, [doNotParse])`:
Example:
```
import cookie from 'react-cookies'
 
componentWillMount() {
  this.state =  { token: cookie.load('token') }
  // => 123456789
}
```

`.loadAll()`:
Example:
```
import cookie from 'react-cookies'
 
componentWillMount() {
  this.state =  { cookies: cookie.loadAll() }
  // => { cookies: { token: 123456789, _ga: GA198712 } }
}
```

`.select([regex])`:
Example:
```
import cookie from 'react-cookies'
 
componentWillMount() {
  this.state =  { tests: cookie.select(/\btest(er|ing|ed|s)?\b/g) }
  // => { tests: { test: 'test', 'testing': 'testing' } }
}
```


## React Cookie Library :books:
**Universal** cookies for React

To install it:
`npm install react-cookie`

To set user cookie : `<CookiesProvider />`
Access and modify cookies using React hooks: `useCookies([dependencies])`
Set a cookie value: `setCookie(name, value, [options])`
Remove a cookie: `removeCookie(name, [options])`
Give access to your cookies anywhere: `withCookies(Component)`


**Additional Resources** :partly_sunny:

**Bookmark / Skim** :star:

- [what is rbac?](https://digitalguardian.com/blog/what-role-based-access-control-rbac-examples-benefits-and-more)
- [react-cookies component](https://www.npmjs.com/package/react-cookies)
- [react-cookie library](https://www.npmjs.com/package/react-cookie)
