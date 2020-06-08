# Bearer Authorization

`signin` attempt, either using **Basic Authentication** or **OAuth**, your service is able to make a **boolean decision** as to the success of the attempt.

Assuming the `signin` was successful, we can **assert** that it would be both more **efficient** and **secure** if the server `“just knew”` that the client making **subsequent requests was allowed to do so**.

**Bearer Tokens** are **encoded** `JSON objects` that “bear” or “contain” enough information for the server to **assert** that any client request that presents a **valid token** must have originated from a client that has previously authenticated themselves using either Basic or OAuth. 

`Authorization: Bearer encoded.jsonwebtoken.here`

Example:
```
app.get('/somethingsecret', bearerToken, (req,res) => {
  res.status(200).send('secret sauce');
});

function bearerToken( req, res, next ) {
  let token = req.headers.authorization.split(' ').pop();
  try {
    if ( tokenIsValid(token) ) { next(); }
  }
  catch(e) { next("Invalid Token") }
}

function tokenIsValid(token) {
  let parsedToken = jwt.verify(token, SECRETKEY);
  return Users.find(parsedToken.id);
}
```

**JSON Web Token** (JWT) is an **open standard** that defines a compact and self-contained way for securely transmitting information between partiesas a `JSON object`. This information can be verified and trusted because it is digitally signed. **JWTs** can be signed using a **secret** or a **public/private** key pair using `RSA` or `ECDSA`.

## When should you use JSON Web Tokens?

**Authorization**: This is the most common scenario for using **JWT**. Once the user is logged in, each subsequent `request` will **include the JWT**, allowing the user to `access routes`, `services`, and `resources` that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.

**Information Exchange**: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content h