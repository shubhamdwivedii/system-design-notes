# How can Push Notifications be implemented ? 

There are multiple ways to implement push notifications:

1. **HTTP Long Polling** : The client initiates a request. The server checks if it has any new notifications. Irrespective of whether or not it has new notifications appropriate response is send and connection is closed. After time X client initiates another request (+ Very easy to implement - notifications are not real time. They depend on X since data retrieval is client initiated. As X decreases overhead on server increases )

2. **HTTP Streaming**: This is very similar to HTTP Long Polling however **the connection is not closed**. The server sends chunked response. So as soon as server receives new notification that it wants to push it can simply write to the socket. ( + lower latency than long polling and almost real time behaviour / overhead of closing connection and re opening reduced - memory usage client side keeps on piling up / ugly hacks etc )

3. **WebSocket**: TCP based protocol provides true two way communication. The server can push data to client any time. 
It enables bi-directional communication between client and the server. **After an initial handshake (initiated from the client side ) the server can push data (JSON objects, regular objects) to the client**. The most stable is combination of **SocketIO** and Node.js which provides cross-browser compatibility. **Also the overhead is lesser than normal HTTP since after the handshake only the frames are sent, no recurring header details are added.**

4. **XMPP**: XMPP is the **Extensible Messaging and Presence Protocol**, a set of open technologies for instant messaging, presence, multi-party chat, voice and video calls.

    - Using the extension called **Jingle**, XMPP can provide an open means to support machine-to-machine or **peer-to-peer** communications across a diverse set of networks. This feature is mainly used for IP telephony (VoIP).
