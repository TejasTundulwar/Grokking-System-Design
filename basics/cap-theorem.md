[CAP Theorem](https://en.wikipedia.org/wiki/CAP_theorem)
====

- Consistency: Users can read and write from any node but they should get same data.
- Availability: Every request to non failing node should get a response, either the data or an error. The system should always be accessible.
- Partition tolerance: Even if some nodes are not able to communicate with each other (but are running) the system should be able to run and operate smoothly.
- CAP theorem implies that in the presence of a network partition, one has to choose between consistency and availability
- CAP is frequently misunderstood as if one has to choose to abandon one of the three guarantees at all times. In fact, the choice is really between consistency and availability only when a network partition or failure happens; at all other times, no trade-off has to be made.
- [ACID](https://en.wikipedia.org/wiki/ACID) databases choose consistency over availability.
- [BASE](https://en.wikipedia.org/wiki/Eventual_consistency) systems choose availability over consistency.
