## Why Ubuntu created snap? Why not reuse Docker?

Docker abstracts few things too many for local workload.
Example: network.
Snap is targetted more toward "run here, but maintain the 'cleanliness' of the local system".
Thus, snap doesn't abstract the network.

Snap target edge computing, where "create 5 instances of redis" doesn't make sense; but "run redis here" does.

Talk by Mark Shuttleworth on snap [ref](https://www.youtube.com/watch?v=0z3yusiCOCk).