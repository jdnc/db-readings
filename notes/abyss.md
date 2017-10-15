# Summary
- Demonstrates the main issues with scaling existing concurrency control algorithms on many core chips 
(simulating upto 1024 core chips). (Experiments with & techniques with variants of 2PL and T/O, OLTP case), and some possible optimizations (including better support from HW)

# Cool implementation technique(s)
- for any contentious datastructure first line of attack should be to partition it in a way that seeks to minimize the contention. (Even better if with the partitioning you can totally eliminate the cause of contention , e.g mutex => lockfree)
- for bottlenecks around getting a monotonially increasing unique number (trx ids) => use batched atomic counter (originally in Silo). (but they ultimately use non-batched)
- For evaluation type papers, often its best to strip away all parts of the system, except for the one you are actually evaluating. E.g they implemented just the concurrency control part of the system. Less interference / less complicated design of evaluation.
(also note how they made deadlock detection trivial, so lock thrashing could be observed more clearly.)

# Cool evaluation techniques(s)
- if you are evaluating with a simulator, do show that the simulator results are realistic for at least some existing system.

# Extensions
- Doesn't explore multi-socket systems at all: but they may be more ubiquitous + more challenging due to cross socket L3 cache contentions, etc
- Needs to concretely evaluate switching between multiple concurrency schemes: how easy is it to train the system to do this dynamically and what are the perf gains.
