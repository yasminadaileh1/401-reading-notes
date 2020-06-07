# OAuth :lock:

## OAUTH2.0 :closed_lock_with_key:

This mean we will use other part as a client (user), **OAuth** is “an open standard for access **delegation** which serves as a way to give users the **ability to grant application access** to services, **without giving the application their password**.
When you login with with other client, you’ve actually given the application (or website) the **keys** to some of your **personal information** and **access levels** at this client.
The application can also do things such as create or delete documents or access other services “as you” in the other client. 

#### How does OAuth work? :unlock:

1. Application spawns the “Login Using `xxx` ” window, **asking for specific permissions**.
2. User **Agrees** to allow this to happen.
3. Remote service (i.e. `Google`) contacts the application with a **one-time-use Code**.
4. The application **calls back** to a special address on the remote service to **exchange that Code for a Token**.
5. Once the **token** has been **granted**, the application will then be able to `contact the remote service`, **using that Token to access information** on behalf of the user.

#### Access Code :key:

**client** needs to grant the application **permission** by:
-  provide an `<a>` tag that will take them to the **service’s authorization page**.
-  **pass** the following information through a **query string** to the authorization server.
(Every service is slightly different in their specific requirements)
-  **variables** like these are part of this initial request:
 - `response_type=code` server wants to receive an authorization code.
 - `client_id=<your client id>` authorization server which app the user is granting access to.
 - `redirect_uri=<your redirect uri>` the auth server which server endpoint to redirect to.
 - `scope=<list of scopes>` the auth server what you want the user to give access to.
 - `state=<anything you want>` place where you can store info to pass to your server if you want.

#### Access Token :open_file_folder:

we need to exchang the `code` provided **to** `token`.

If the users **grants access** to the application, the authorization server will redirect to a provided redirect URI callback with a`“code”`. Once we have this `code`, you can **exchange** it for an `access token` by making a `POST` request to the authorization server and providing the following information:
- `grant_type=authorization_code`.
- `code=<the code your received>`.
- `redirect_uri=REDIRECT_URI`  must be same as the **redirect URI** your client provided.
- `client_id=<your client id>` tells the authorization server **which application is making the requests**.
- `client_secret=<your client secret>` application registered with the **client_id**.
- Once you get an access token, you can **use it to make API calls** to the service on behalf of that user.


### Additional Resources :pager:

**Read** :books:

- [OAuth2 simplified](https://aaronparecki.com/oauth-2-simplified/)

**Videos** :smirk:

- [What is OAuth Really All About?](https://www.youtube.com/watch?v=t4-416mg6iU)


**Bookmark / Skim** :star:

- [OAuth wiki](https://en.wikipedia.org/wiki/OAuth)
- [Build a Node API with OAuth](https://developer.okta.com/blog/2018/08/21/build-secure-rest-api-with-node)




