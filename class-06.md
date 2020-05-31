# HTTP and REST :repeat:

## HTTP :satellite:

**What is the HTTP :heavy_exclamation_mark:**

**The Hyper Text Transfer Protocol** (HTTP) is a **stateless request-response** application layer protocol. HTTP is **used to build distributed**, **collaborative**, **hypermedia** **information** **systems**.
The **HTTP** specification defines **how** requests and responses should be **formatted**, but not what a service should represent. HTTP is often associated with serving `.html` files but is also used to transfer **images**, **videos**, `.json`, `.xml`, binary executables, and much more.

**HTTP Requests**
A HTTP/1.1 request is formatted in text and transferred using TCP. The first line of the request contains the `METHOD`, `URL`, and `HTTP VERSION`.

| **Method** | **Description**                                                                                                                                                                             |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CONNECT    | This specification reserves the method name CONNECT for use with a proxy that can dynamically switch to being a tunnel (e.g. SSL tunneling).                                                |
| DELETE     | The DELETE method requests that the origin server delete the resource identified by the Request-URI.                                                                                        |
| GET        | The GET method retrieves whatever information (in the form of an entity) is identified by the Request-URI.                                                                                  |
| HEAD       | The HEAD method is identical to GET except that the server MUST NOT return a message-body in the response.                                                                                  |
| OPTIONS    | The OPTIONS method represents a request for information about the communication options available on the request/response chain identified by the Request-URI.                              |
| POST       | The POST method is used to request that the origin server accept the entity enclosed in the request as a new subordinate of the resource identified by the Request-URI in the Request-Line. |
| PUT        | The PUT method requests that the enclosed entity be stored under the supplied Request-URI.                                                                                                  |
| TRACE      | The TRACE method is used to invoke a remote, application-layer loop-back of the request message.                                                                                            |

**HTTP Response** 
A HTTP/1.1 response is also formatted in text and transferred using TCP. The first line of the response contains the `HTTP VERSION`, `STATUS CODE`, and `STATUS MESSAGE`.

**Additional Resources** :partly_sunny:

1. Videos: [http and rest](https://www.youtube.com/watch?v=Q-BpqyOT3a8)

**Bookmark / Skim** :star:

- [http basics](https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177)
- [what is ReST](https://restfulapi.net/)
- [swagger documentation](https://swagger.io/docs/)
- [swagger editor](https://editor.swagger.io/)
- [http reference](https://code-maze.com/the-http-reference/)
- [rest reference](https://www.restapitutorial.com/lessons/httpmethods.html)
