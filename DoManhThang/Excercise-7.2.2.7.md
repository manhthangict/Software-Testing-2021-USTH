### Excercise-7.2.2.7 The graph defined by the following sets:
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

a) Draw a graph
![image](https://user-images.githubusercontent.com/81274225/121561952-2eb27900-ca43-11eb-8e74-6cd930aa2f35.png)

b) List the eight test requirements for Edge-Pair Coverage (only the length two subpaths)

[1,3,1] [1,2,3] [1,2,1] [2,3,1] [2,1,3] [2,1,2] [3,1,3] [3,1,2]

c) Does the set of test paths from part (a) above satisfy Edge-Pair Coverage? If not, state what is missing

p2 and p3 are not covered [2; 1; 2]; [3; 1; 3]

d) Consider the prime path [3, 1, 3] and path p2. Does p2 tour the prime path directly? With a sidetrip?

p2 does not tour prime path [3,1,3]
