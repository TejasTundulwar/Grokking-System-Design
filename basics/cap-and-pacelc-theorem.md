[CAP Theorem](https://en.wikipedia.org/wiki/CAP_theorem)
====

- Consistency: Users can read and write from any node but they should get same data.
- Availability: Every request to non failing node should get a response, either the data or an error. The system should always be accessible.
- Partition tolerance: Even if some nodes are not able to communicate with each other (but are running) the system should be able to run and operate smoothly.
- CAP theorem implies that in the presence of a network partition, one has to choose between consistency and availability
- CAP is frequently misunderstood as if one has to choose to abandon one of the three guarantees at all times. In fact, the choice is really between consistency and availability only when a network partition or failure happens; at all other times, no trade-off has to be made.
- [ACID](https://en.wikipedia.org/wiki/ACID)(Atomicity, Consistency, Isolation, Durability) databases, such as RDBMSs like MySQL, Oracle, and Microsoft SQL Server choose consistency over availability.
- [BASE](https://en.wikipedia.org/wiki/Eventual_consistency) (Basically Available, Soft-state, Eventually consistent) systems choose availability over consistency.

## PACELC Theorem
<img width="767" alt="image" src="https://user-images.githubusercontent.com/5825394/136715780-5d734fa2-ef82-4977-b548-28f350c31f20.png">

If Partition is not there choose between Latency and Consistency and if Partition is there then choose between Consistency and Availability.

## Examples
- Dynamo and Cassandra are PA/EL systems: 
  - They choose **availability over consistency** when a partition occurs; otherwise, they choose lower **latency**.
- BigTable and HBase are PC/EC systems: 
  - They will **always choose consistency**, giving up availability and lower latency. (They are fine with db not being available but it should have data consistency always)
- MongoDB can be considered PA/EC (default configuration): (Chooses Availability if Partition is there , if partition not there chooses Consistency)
  - MongoDB works in a primary/secondaries configuration. In the default configuration, all writes and reads are performed on the primary. As all replication is done asynchronously (from primary to secondaries), **when there is a network partition in which primary is lost or becomes isolated on the minority side, there is a chance of losing data that is unreplicated to secondaries, hence there is a loss of consistency during partitions**. Therefore it can be concluded that in the case of a network partition, MongoDB chooses availability, but otherwise guarantees consistency. Alternately, when MongoDB is configured to write on majority replicas and read from the primary, it could be categorized as PC/EC.
