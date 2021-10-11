Consistent Hashing
====

## Simple hashing
Problems of simple hashing function `key % n` (`n` is the number of servers):
- It is not horizontally scalable. Whenever a new cache host is added to the system, all existing mappings are broken.
- It may not be load balanced, especially for non-uniformly distributed data. Some servers will become hot spots.

<img width="729" alt="image" src="https://user-images.githubusercontent.com/5825394/136717525-e06c08e4-4662-4a54-badd-28cb2a943f2f.png">


## Consistent Hashing
- Consistent hashing maps a key to an integer.
- Imagine that the integers in the range are placed on a ring such that the values are wrapped around.
- Given a list of servers, hash them to integers in the range.
- To map a key to a server:
  - Hash it to a single integer.
  - Move clockwise on the ring until finding the first cache it encounters.
- When the hash table is resized (a server is added or deleted), only `k/n` keys need to be remapped (`k` is the total number of keys, and `n` is the total number of servers).
- To handle hot spots, add “virtual replicas” for caches.
  - Instead of mapping each cache to a single point on the ring, map it to multiple points on the ring (replicas). This way, each cache is associated with multiple portions of the ring.
  - If the hash function is “mixes well,” as the number of replicas increases, the keys will be more balanced.

<img width="748" alt="image" src="https://user-images.githubusercontent.com/5825394/136717540-5c36a652-7fb8-4310-8912-1d0f4d461c3f.png">
<img width="449" alt="image" src="https://user-images.githubusercontent.com/5825394/136717551-89f5354e-af4b-4ec9-9b1c-0cd2546fafa9.png">
<img width="958" alt="image" src="https://user-images.githubusercontent.com/5825394/136717558-01a395aa-7ed7-4355-a089-e07ac66e73fe.png">
<img width="836" alt="image" src="https://user-images.githubusercontent.com/5825394/136717567-bc695599-67e8-4287-acd2-aa8a42f85998.png">
<img width="663" alt="image" src="https://user-images.githubusercontent.com/5825394/136717574-664562df-4689-4a4c-a177-08bfd329c9b2.png">
<img width="696" alt="image" src="https://user-images.githubusercontent.com/5825394/136717584-1fd248be-6d2d-4756-8834-4acc8346793c.png">

For detailed info go [here](consistent_hashing_complete.md)
