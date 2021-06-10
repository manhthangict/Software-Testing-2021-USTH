### 7.2.2.7 The graph defined by the following sets:
* N = {1, 2, 3}
* N0 = {1}
* Nf = {3}
* E = {(1, 2), (1, 3), (2, 1), (2, 3), (3, 1)}
Also consider the following (candidate) test paths:
* p1 = [1, 2, 3, 1]
* p2 = [1, 3, 1, 2, 3]
* p3 = [1, 2, 3, 1, 2, 1, 3]
* p4 = [2, 3, 1, 3]
* p5 = [1, 2, 3, 2, 3]

a) Which of the listed paths are test paths? For any path that is not a test path, explain why not?

p1 does not terminate at a final node. p4 does not start at an initial node. p5 includes an edge that does not exist in the graph.

b) List the eight test requirements for Edge-Pair Coverage (only the length two subpaths)

[1, 2, 1] [1, 2, 3] [1, 3, 1] [2, 1, 2] [2, 1, 3] [2, 3, 1] [3, 1, 2] [3, 1, 3]

c) Does the set of test paths from part (a) above satisfy Edge-Pair Coverage? If not, state what is missing

No, p2 and p3 do not tour either of the following edge-pairs: [2, 1, 2] [3, 1, 3]

d) Consider the prime path [3, 1, 3] and path p2. Does p2 tour the prime path directly? With a sidetrip?

No, p3 tour the prime path with the sidetrip [1, 2, 1]
