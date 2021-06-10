### 7.2.2.5 Answer questions a–g for the graph defined by the following sets:
* N = {1, 2, 3, 4, 5, 6, 7}
* N0 = {1}
* Nf = {7}
* E = {(1, 2),(1, 7),(2, 3),(2, 4),(3, 2),(4, 5),(4, 6),(5, 6),(6, 1)}

a) Draw the graph

![image](https://user-images.githubusercontent.com/81274225/121451851-865fce80-c9c8-11eb-8bb2-665226a84ae9.png)

b) List the test requirements for Edge-Pair Coverage:

* [1, 2, 3] [1, 2, 4] [1, 7] 
* [2, 3, 2] [2, 4, 5] [2, 4, 6]
* [3, 2, 3] [3, 2, 4]
* [4, 5, 6] [4, 6, 1] 
* [5, 6, 1] 
* [6, 1, 2] [6, 1, 7]

c) Does the given set of test paths satisfy Edge-Pair Coverage? If not, state what is missing

No, the Edge-Pair missing are:
* The test path p1 misses [2,3,2], [3,2,3], [3,2,4], [2,4,6] and [4,6,1]
* The test path p2 misses [2,4,5], [4,5,6]
* The test path p3 misses [4,6,1], [2,4,6]

d) Consider the simple path [3, 2, 4, 5, 6] and test path [1, 2, 3, 2, 4, 6, 1, 2, 4, 5, 6, 1, 7]. Does the test path tour the simple path directly? With a sidetrip? If so, write down the sidetrip.

No, it tour the simple path with a sidetrip [4, 6, 1, 2, 4]

e) List the test requirements for Node Coverage, Edge Coverage, and Prime Path Coverage on the graph

* Edge coverage: TR = {[1, 2] [1, 7] [2, 3] [2, 4] [3, 2] [4, 5] [4, 6] [5, 6] [6, 1]}
* Node coverage: TR = {1, 2, 3, 4, 5, 6, 7}
* Prime paths: TR = [3, 2, 4, 5, 6, 1, 7] [2, 4, 5, 6, 1, 2] [1, 2, 4, 5, 6, 1] [3, 2, 4, 6, 1, 7] [5, 6, 1, 2, 4, 5] [6, 1, 2, 4, 5, 6] [4, 5, 6, 1, 2, 4] [4, 5, 6, 1, 2, 3] [2, 4, 6, 1, 2] [1, 2, 4, 6, 1] [6, 1, 2, 4, 6] [4, 6, 1, 2, 3] [4, 6, 1, 2, 4] [3, 2, 3] [2, 3, 2]

f) List test paths from the given set that achieve Node Coverage but not Edge Coverage on the graph

* Test path achieve Node Coverage: [1, 2, 3, 2, 4, 5, 6, 1, 7] but it's still lack of [4, 6]  
=> No test path achieve Node Coverage but not Edge Coverage on the graph.

g) List test paths from the given set that achieve Edge Coverage but not Prime Path Coverage on the graph
It's impossible from the given set on the graph
