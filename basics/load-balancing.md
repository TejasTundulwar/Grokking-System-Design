Load Balancing (LB)
====

Help scale horizontally across an ever-increasing number of servers.

## LB locations
- Between user and web server
<img width="747" alt="image" src="https://user-images.githubusercontent.com/5825394/136702177-2705ea3d-dddb-45b0-9d3f-946ff8125382.png">
- Between web servers and an internal platform layer (application servers, cache servers)
- Between internal platform layer and database
<img width="971" alt="image" src="https://user-images.githubusercontent.com/5825394/136702196-3953d364-5343-48e9-a341-b8acf7435ed4.png">


## Algorithms
- Least connection
- Least response time
- Least bandwidth
- Round robin
- Weighted round robin
- IP hash

## Explanation of Algorithms
- Least Connection Method
  - Directs traffic to the server with the **fewest active connections**. 
  - Useful when large number of **unevenly distributed persistent client connections** between the servers.
- Least Response Time Method 
  — Directs traffic to the server with the **fewest active connections** and the **lowest average response time**.
- Least Bandwidth Method 
  - This method selects the server that is **currently serving the least amount of traffic** measured in megabits per second (Mbps).
- Round Robin Method 
  — This method **cycles through a list of servers** and sends each new request to the next server.
  - Most useful **when the servers are of equal specification** and there are **not many persistent connections**.
- Weighted Round Robin Method 
  — The weighted round-robin scheduling is designed to better handle **servers with different processing capacities**. Each **server is assigned a weight** (an integer value that indicates the processing capacity). 
  - Servers with **higher weights receive new connections** before those with less weights and servers with higher weights get more connections than those with less weights.
- IP Hash 
  — Under this method, a **hash of the IP address** of the client is calculated to redirect the request to a server.

## Redundant Load Balancers
The **load balancer can be a single point of failure**; to overcome this, a second load balancer can be connected to the first to **form a cluster. Each LB monitors the health of the other** and, since both of them are equally capable of serving traffic and failure detection, in the event the **main load balancer fails, the second load balancer takes over**.

<img width="852" alt="image" src="https://user-images.githubusercontent.com/5825394/136702631-1a6c8d4c-095d-4bc8-ab6f-9e77940a1476.png">


## Implementation
- Smart clients
- Hardware load balancers
- Software load balancers
