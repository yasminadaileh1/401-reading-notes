# TCP Servers

## Event Queues
**Event Queues** is a repository where events from an application are held prior to being processed by a receiving program or system. **Event queues** are often used in the context of an enterprise messaging system.
Much of the NodeJS architecture is built around the use of **events**. All objects that **emit events** in NodeJS are instances of the EventEmitter constructor.


`EventEmitter class` Use in components with the `@Output` directive to emit custom events synchronously or asynchronously, and **register handlers** for those events by subscribing to an instance.
```
class EventEmitter<T> extends Subject {
  constructor(isAsync: boolean = false)
  emit(value?: T)
  subscribe(generatorOrNext?: any, error?: any, complete?: any): Subscription
}
```

In practical applications, multiple `“disconnected”` services can communicate with one another using **various protocols** using proprietary **APIs**. Generally, this is done through a central `“Hub”` server (or `Queue`) which receives all inbound messages, scrubs the content, and then broadcasts those messages to **connected subscribers**.

## OSI Model
The **purpose** of the OSI reference model is to **guide** *vendors* and *developers* so the digital communication products and software programs they create can **interoperate**, and to **facilitate a clear framework** that describes the functions of a networking or telecommunication system.
This **seven layer OSI** model has continued to accurately describe the different processes in computer networking, and is still widely used as a point of reference while working in networked systems today.

## Internet Protocol Suite
The Internet Protocol Suite is the conceptual model for the protocols used by the internet. It is often referred to as TCP/IP because the IP and TCP were the original protocols in the suite.

#### **TCP**
**The Transmission Control Protocol (TCP)** is widely used by application layer protocols in the Internet Protocol Suite. TCP creates a **two way communication between two hosts** and provides reliable, ordered, and error checked byte streams between the applications. 

**TCP HEADER**
```
Byte 0: Source port
Byte 3: Destination port
Byte 4: Sequence number
Byte 8: Acknowledgement number
Byte 12: Data Offset, NS flag, and 3 undefined bits
Byte 13: CWR, ECE, URG, ACK, PSH, RST, SYN, and FYN flags
Byte 14: Window size
Byte 16: Checksum
Byte 18: Urgent pointer
Byte 20: Options
```



