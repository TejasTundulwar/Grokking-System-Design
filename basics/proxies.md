Proxies
====

- A proxy server is a piece of software or hardware that **acts as an intermediary for requests** from clients seeking resources from other servers.
<img width="614" alt="image" src="https://user-images.githubusercontent.com/5825394/136712497-2edb8875-2cf2-429f-8701-f277fd32cf86.png">
  
  - Filter requests
  - Log requests
  - Transform requests (encryption, compression, etc)
  - [Cache](caching.md)
  - Batch requests
    - Collapsed forwarding: enable multiple client requests for the same URI to be processed as one request to the backend server
    - Collapse requests for data that is spatially close together in the storage to minimize the reads

- Can reside on the client’s local server or anywhere between the client and the remote servers.
- Generally allows only clients in a particular user group to store and forward internet services like DNS, web pages etc

Types of proxies
===
- Open Proxy: Anyone on the internet is able to use this as a forwarding service.
  - Anonymous Proxy: Identifies as server but does not disclose its initial IP address. Although it can be discovered easily can help clients hide their IP Address.
  - Transparent Proxy: Identifies as server and using the HTTP headers discloses the initial IP address. Useful in cacheing websites.
- Reverse Proxy: Requests resources to other servers on behalf of the client. These resources are then returned to the client appearing as if they were retrieved by the proxy itself.
