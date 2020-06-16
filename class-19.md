# Message Queues

## Message Queues

A Queue server runs **independently**, and is tasked with **routing** events and messaging between clients Client can **“publish”** a message into the server, or **“subscribe”** to receive messages by type.
The Queue server has the ability to see **which clients are connected**, to which Queues they are attached and further, to which events they are subscribed. It must further ensure that subscribed clients can **`“catch up”`** and pull down any messages that they might have missed during a period of `disconnection` with the server.

### What is a message?
- A message is a **package** of information, **categorized** by `queue` and `event`
- `queue` - Which general bucket does this message belong
i.e. `“Database Events”`, `“Filesystem Events”`, `“Network Events”`, etc
- `event` - What event has happened
i.e. `“delete`, `add`, `update`, `connection lost`, `error”`, etc.
- `payload` - data associated with the event
i.e. “`record id`, `record information`, `error text`”, etc.

## Real Time vs Queued Messaging
 `“Queue”` will keep track of the **delivery status** of every `event`/`message`. Any broadcast that is not received by a subscriber will remain “in the queue” until it can be delivered. In this type of systems, rather than a broadcasting of messages, clients will likely “poll” the server to retrieve any messages “in the queue” for them, on their own timeline/schedule.


**Additional Resources** :partly_sunny:

**Bookmark / Skim** :star:

- [Rooms and Namespaces](https://socket.io/docs/rooms-and-namespaces/)
- [Rooms and Namespaces](https://socket.io/docs/emit-cheatsheet/)