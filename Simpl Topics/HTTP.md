## HTTP (Hyper Text Transfer Protocol)

**HTTP** is a **set of rules** that **runs on top of the TCP/IP** suite of protocols and **defines how files are to be transferred between clients and servers** on the world wide web.

**HTTP** is a **Protocol** for **fetching resources** such as HTML documents. 

It is the foundation of any data exchange on the Web and it is a **client-server protocol**, which means **requests** are initiated by the **recipient**, usually the Web browser. 


A complete document is reconstructed from the different sub-documents fetched, for instance, text, layout description, images, videos, scripts, and more. 


Communication between client computers and web servers is done by sending **HTTP Requests** and receiving **HTTP Responses**


![http1](./http_works.png)


**HTTP** is an **extensible protocol** which has evolved over time. It is an application layer protocol that is **sent over** **TCP**, or over a **TLS-encrypted TCP connection**, though any reliable transport protocol could theoretically be used.


## Components of HTTP-based systems 

**HTTP** is a **client-server protocol**: requests are sent by one entity, the user-agent (or a proxy on behalf of it). Most of the time the user-agent is a **Web browser**, but it can be anything, for example, a robot that crawls the Web to populate and maintain a search engine index.

Each individual request is sent to a server, which handles it and provides an answer called the **response**.

Between the client and the server there are numerous entities, collectively called **proxies**, which perform different operations and act as **gateways** or **caches**, for example.

![http2](./http_proxies.png)


In reality, there are more computers between a browser and the server handling the request: there are routers, modems, and more. Thanks to the **layered design of the Web**, these are **hidden** in the **network** and **transport layers**.

**HTTP** is on **top**, at the **application layer**.

_See OSI Model_


### The Client: 

The **user-agent** is any tool that acts on behalf of the user.

Like web browsers, any app/program.

The **User-Agent** (**Browser**) is **always** the entity initiating the request. It is **never the server**. 


### The Web Server: 

A **server** serves the document as requested by the client. 


A server appears as only a **single machine virtually**; but it may **actually be a collection of servers** sharing the load (load balancing), or a complex piece of software interrogating other computers (like cache, a DB server, or e-commerce servers), totally or partially generating the document on demand.

### The Proxies: 

Between the Web browser and the server, **numerous computers and machines relay the HTTP messages**. 

Due to the layered structure of the Web stack, **most of these operate at the transport, network or physical levels**, becoming transparent at the HTTP layer and potentially having a significant impact on performance.

Those operating at the application layers are generally called **proxies**.

Proxies may perform numerous functions:

- **Caching** (the cache can be public or private, like the browser cache)
- **Filtering** (like an antivirus scan or parental controls)
- **Load balancing** (to allow multiple servers to serve different requests)
- **Authentication** (to control access to different resources)
- **Logging** (allowing the storage of historical information)


## Basic Aspects of HTTP 

### HTTP is simple: 

HTTP is generally designed to be simple and human readable.

### HTTP is extensible: 

Since HTTP/1.0, HTTP headers make this protocol easy to extend and experiment with. 

### HTTP is stateless, but not sessionless 

**HTTP is stateless**: there is **no link between two requests** being **successively carried out on the same connection**.

This immediately has the prospect of being problematic for users attempting to interact with certain pages coherently, for example, using e-commerce shopping baskets. 

But while the core of HTTP itself is stateless, **HTTP cookies allow the use of stateful sessions**. 

Using header extensibility, **HTTP Cookies are added to the workflow**, **allowing session creation on each HTTP request to share the same context, or the same state**.


### HTTP and connections:

**A connection is controlled at the transport layer**, and therefore fundamentally out of scope for **HTTP**. 

HTTP doesn't require the underlying transport protocol to be connection-based; **it only requires it to be reliable**, or not lose messages (at minimum, presenting an error in such cases).

Among the two most common transport protocols on the Internet, **TCP is reliable** and **UDP isn't**.

HTTP therefore relies on the **TCP** standard, **which is connection-based**.

Before a client and server can exchange an HTTP request/response pair, **they must establish a TCP connection**, a process which **requires several round-trips**.


The default behavior of HTTP/1.0 is to **open a separate TCP connection for each HTTP request/response pair**. This is less efficient than sharing a single TCP connection when multiple requests are sent in close succession.


HTTP/1.1 introduced **pipelining** (which proved difficult to implement) and **persistent connections**: the underlying TCP connection can be partially controlled using the **Connection header**.

HTTP/2 went a step further by **multiplexing messages over a single connection**, helping keep the connection warm and more efficient.


## HTTP Flow 

When a client wants to communicate with a server, either the final server or an intermediate proxy, it performs the following steps:

1. **Open a TCP connection**: The TCP connection is used to send a request, or several, and receive an answer. **The client may open a new connection, reuse an existing connection, or open several TCP connections to the servers**.

2. **Send an HTTP message**: HTTP messages (before HTTP/2) are human-readable. With HTTP/2, these simple messages are encapsulated in frames, making them impossible to read directly, but the principle remains the same.

3. **Read the response** sent by the server.


## HTTP Headers: 

HTTP header fields **provide required information about the request or response**, or about the object sent in the message body. 

There are four types of HTTP message headers:

1. **General-header**: These header fields have general applicability for both request and response messages.

2. **Client Request-header**: These header fields have applicability only for request messages.

3. **Server Response-header**: These header fields have applicability only for response messages.

4. **Entity-header**: These header fields define meta information about the entity-body or, if no body is present, about the resource identified by the request.


Headers can be grouped according to their contexts:

1. **Request headers** contain more information about the resource to be fetched, or about the client requesting the resource.

2. **Response headers** hold additional information about the response, like its location or about the server providing it.

3. **Representation headers** contain information about the body of the resource, like its MIME type, or encoding/compression applied.

4. **Payload headers** contain representation-independent information about payload data, including content length and the encoding used for transport.


## HTTP2 (Introduced in 2015 (based on Google's SPDY from 2010)) - Key Features 

1. It **introduces concept of a server push**, where the server anticipates the resources that will be requried by the client and pushes them prior to the client making requests. 

    The client retains authority to deny server push.
    In most cases, server push improves efficiency by a lot. 

2. **Introduces the concept of multiplexing** that interleaves the request and responses without head-of-line blocking and does so over **a single TCP connection**. 

3. HTTP2 is a **binary protocol** ie: only binay commands in form of **0s and 1s** are transmitted over the wire. 

    The binary framing layer divides the messages into frames that are segregated based on their type - **Data or Header**

    This features **increases security, compression and multiplexing**.


## HTTP1 vs HTTP2 

- HTTP1: For **every TCP connection, there is only one request and one response**.
- HTTP2: **Uses multiplexing**, where over a **single TCP connection** resources to be delivered are **interleaved** and **arrive at the client almost at the same time**. 


- HTTP1: Uses **basic authentication scheme** which is unsafe since **username and passwords are transmitted in clear text or base64 encoded**. 
- HTTP2: Better equipped to deal with them due to new **TLS features** like connection error of type Inadequate_Security


- HTTP1: Provides support for **caching via the If-Modified-Since header**.
- HTTP2: With the **server push feature** if the client finds the **resources are already present in the cache**, it can c**ancel the pushed stream**.

- HTTP1: **Is Textual (usually base64)**
- HTTP2: **Is Binary (0s and 1s)**


## HTTP vs HTTPS 

1. **HTTP is unsecured** while **HTTPS is secured**. 
2. **HTTP sends data over port 80** while **HTTPS uses port 443**. 
3. **HTTP operates at application layer**, while **HTTPS operates at transport layer**
4. **No SSL certificates are required for HTTP**, with **HTTPS requires SSL certificate signed by a CA**.
5. **HTTP doesn't require domain validation**, where as **HTTPS requires at least domain validation** and certain certificates even require legal document validation. 
6. **No encryption in HTTP**, with **HTTPS the data is encrypted before sending**.  

_That should be enough_

_See SSL/TLS Next_