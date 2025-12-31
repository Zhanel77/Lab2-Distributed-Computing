# Lab2-Distributed-Computing

## Lab 2 — Replication and Causality in Distributed Systems

In this lab, I implemented a distributed key-value store with multiple nodes (A, B, C) using HTTP communication and Lamport logical clocks. The goal was to study replication, causality, and consistency in a distributed system.

### What was done

- Each node runs an independent server and stores key-value pairs.
- Updates are replicated to peer nodes using HTTP requests.
- Lamport timestamps are used to order events and resolve conflicts.

### The system uses Last-Write-Wins (LWW) to handle concurrent writes.

1. Tested Scenarios

***Scenario A — Delay / Reorder:***
Artificial delay was added to replication to show that different nodes may apply updates in different orders.

***Scenario B — Concurrent Writes:***
The same key was updated simultaneously on different nodes. The system converged using LWW, choosing the update with the highest timestamp.

***Scenario C — Temporary Outage:***
One node was stopped during updates. After restarting, it synchronized with peers and reached eventual consistency.

## Conclusion

This lab demonstrates how distributed systems handle concurrency, failures, and consistency using replication, logical clocks, and conflict resolution strategies.
