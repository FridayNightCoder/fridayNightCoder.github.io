---
title: Architecture 
weight: 10
menu:
  notes:
    name: Architecture
    identifier: architecture
    parent: tiny-url
    weight: 10
---
{{< note title="Architecture">}}

### How to generate the tiny URL
Need to know what the composition is going to be and the size
for example, all lower case + all digits = 36 characters
for a tiny URL of size 6 we would have 36^6 = 2Billion
for 8 characters it would be 36^8 ~= 3Billion
Hashing might sounds like a good idea (sha/md5) but because we need to shorten those we would have a lot of collisions so we 
would need to address those.

A popular option is to use something like an key generating 
service. Keeps track of keys that have been used. Avoid double
generation of keys.

Don't use a DB with multi-leader replication (that use last write wins).

You can use partioning on the key to split the data evenly accross
partitions. 

We might get a lot of hits for certains more popular keys and for those because they are mainly reads we can leverage a cache.
A good eviction policy would be LRU (last recently used).
{{< /note >}}

{{< note title="Database">}}

### Databases
NoSQL with single-leader (SLM), MongoDB, Cassandra?

### Load balancing
Decouple the reads and the writes into separate microservices.
We have a 100:1 r/w ratio.
Maybe using consistent hashing
{{< /note >}}