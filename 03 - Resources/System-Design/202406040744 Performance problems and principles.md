---
date: 2024-06-04T07:44
tags:
  - Architecture
  - System-Design
---
**Performance problems** occur due to a queue building up somewhere. Those queues can be: `Network socket queue` | `DB IO queue` | `OS run queue`

**Reasons for queue building up:**
- <u>Inefficient slow processing</u> (the algorithm that was used in the code is too slow);
- <u>Serial resource access</u> (a programs utilizing only one thread to operate, while it can use multiple threads);
- <u>Limited resource capacity</u> (Not enough RAM, CPU or Memory)

### The GOAL is to identify a queue build up

Types of a request processing:
- Serial Request processing (One request at a time)
- Concurrent Request processing (Multiple requests at a time)

## Performance principles
- **Efficiency** (Serial request processing)
	- <u>Efficient Resource Utilization</u>
		- IO
		- CPU
	- <u>Efficient Logic</u>
		- Algorithm
		- DB Queries
	- <u>Caching</u>
- **Concurrency** (Concurrent request processing)
	- <u>Hardware</u>
	- <u>Software</u>
		- Querying
		- Coherence 
- **Capacity**
