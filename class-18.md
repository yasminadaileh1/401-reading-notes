# Socket.io

## Web Sockets
It's a **communication Protocol** which provides bidirectional communication **between the Client and the Server** over a **TCP** connection. When clients trigger the request to the Server it **does not close the connection** on receiving the response, it rather persists and **waits** for Client or server **to terminate the request**.

## Socket.io
It is a **library** which enables real-time and **full duplex communication** between the *Client* and the *Web servers*.It uses the **WebSocket protocol** to provide the **interface**.
It is divided into **two parts**:
- **Client Side**: it is the library that runs **inside the browser**.
- **Server Side**: It is the library for **Node.js**.

## Connections
connect directly to a server with a **keep-alive** type of connection.

## Messaging
**Socket.io** uses the same methodology/terminology **events** are sent with `emit()` and **received** with `on()`, all parts of the application can **emit** and **hear** events. **No** outside application can **participate** in these **events natively**. With **Socket.io**, the entire purpose is **to have events shared between `‘disconnected’` participants**. Through a mediator (server), clients connect, emit events, and respond to events from the server.

A typical flow works like this:
- Client Applications 1, 2, 3, x … connect to a running Socket.io server
 - Clients can join the common pool of connections or coalesce into groups/subgroups, if the server has been setup in this manner
- Client Application 1 emits an event called ‘speak’ to the server, with the data ‘Hello World’
- Server has an `on('speak', (data) => {})` which **“hears”** that event
- Upon processing the event, the server may elect to
 - `broadcast()` the event itself or `emit()` an event of it’s own.
 - Messages can be sent to individual clients, groups, or sub-groups of clients
- Other client applications that have connected into the server may have a listener on that event type, can then “hear” it as well…
 - i.e. `socket.on('incoming-message', text => console.log(text)`
- Not every client will have a listener for every event.
- The server may not have a listener for every event a client sends.

**Additional Resources** :partly_sunny:

**Bookmark / Skim** :star:

- [Web Sockets](https://en.wikipedia.org/wiki/WebSocket)
- [Socket.io Tutorial](https://www.tutorialspoint.com/socket.io/)
- [Socket.io vs Web Sockets](https://www.educba.com/websocket-vs-socket-io/)
- [Socket.io Documentation](https://socket.io/docs/)
- [Socket.io Server API](https://socket.io/docs/server-api)
- [Socket.io Client API](https://socket.io/docs/client-api)

