Redundancy
====

- Redundancy: **duplication of critical data or services** with the intention of increased reliability of the system.
- Server failover
  - Remove single points of failure and provide backups (e.g. server failover).
- Shared-nothing architecture
  - Each node can operate independently of one another.
  - No central service managing state or orchestrating activities.
  - New servers can be added without special conditions or knowledge.
  - No single point of failure.

<img width="471" alt="image" src="https://user-images.githubusercontent.com/5825394/136712724-742be116-49e2-4666-a429-fcd9feb33c19.png">

Replication
===
- Sharing **information (copying)** to ensure consistency between redundant resources **to improve reliability, fault-tolerance, or accessibility**.
- This is used widely in DBMS ususally with a primary and secondary relationship between the replicas. First a change is made to the primary replica and then it is rippled through the other replicas. Secondary replicas send a acknowledgment once the update is recieved.
