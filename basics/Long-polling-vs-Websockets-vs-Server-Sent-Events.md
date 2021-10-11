Long-Polling vs WebSockets vs Server-Sent Events
===
What is the difference between Long-Polling, WebSockets, and Server-Sent Events?
### Normal HTTP
- The client opens a connection and requests data from the server.
- The server calculates the response.
- The server sends the response back to the client on the opened request.
<img width="562" alt="image" src="https://user-images.githubusercontent.com/5825394/136733945-9b0a5925-f41d-4a86-9de4-845300f9b13c.png">

### AJAX Polling
This is when client opens a connection and **keeps pinging the server at short intervals** to get a response. Its like pinging to get an update.

Lifecycle:
- The client opens a connection and requests data from the server using regular HTTP.
- The **requested webpage** sends **requests to the server at regular intervals** (e.g., 0.5 seconds).
- The **server** calculates the **response** and sends it back, just like regular HTTP traffic.
- The **client repeats** the above three steps periodically to get updates from the server.

<img width="631" alt="image" src="https://user-images.githubusercontent.com/5825394/136734166-9441a3a3-c1cd-4027-9346-e325acfbeb6a.png">

### HTTP Polling
- Also called "Hanging GET", **client makes a requests and waits for server to respond**.
- The client requests information from the server exactly as in normal polling, but with the expectation that the server may not respond immediately. 
- Whenever the data is available the serversends a full response back to the client. 
- Once the client gets a response it immediately sends another request so the server will always have pending request to respond for.
- Each Long-Poll request has a timeout. The client has to reconnect periodically after the connection is closed due to timeouts.

<img width="626" alt="image" src="https://user-images.githubusercontent.com/5825394/136734559-f23abd03-9acc-45b8-8777-e15443e78308.png">

### WebSockets
- Full duplex
-  It provides a persistent connection between a client and a server that both parties can use to start sending data at any time.
-  Client establishes connection via a Websocket Handshake.
-  Facilitates real time data transfer with lower overheads.
<img width="642" alt="image" src="https://user-images.githubusercontent.com/5825394/136734858-39389c5f-5578-486f-a1b2-3e8db2ab682b.png">

### Server Sent Events
- Like the push mechanism in pubsub.
- Client opens a long-term connection with the client, server uses this connection to send the data to client whenever available.
- Excellent when need to transfer data in real-time and server is generating data in a loop and will be sending multiple events to the client.
<img width="613" alt="image" src="https://user-images.githubusercontent.com/5825394/136735085-5eb63ee2-bed7-44a9-846d-584d6186f375.png">



