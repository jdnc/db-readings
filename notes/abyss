# Summary
- Can current concurrency control algorithms be linearly scalable on many core chips? (Experiments with 2PL and T/O).

# Cool technique(s)
- bottlenecks around getting a monotonially increasing unique number (trx ids) => use batched atomic counter (originally in Silo). (but they ultimately use non-batched)
- For evaluation type papers, often its best to strip away all parts of the system, except for the one you are actually evaluating. E.g they implemented
just the concurrency control part of the system. Less interference / less complicated design of evaluation.

# Cool evaluation techniques(s)
- if you are evaluating with a simulator, do show that the simulator results are realistic for at least some existing system.
- 

# Extensions
- Doesn't explore multi-socket systems at all: but they may be more ubiquitous + more challenging due to cross socket L3 cache contentions, etc
