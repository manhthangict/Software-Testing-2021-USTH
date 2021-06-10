### 7.5.1 Use the class BoundedQueue2 for questions a–f below. A compilable version is available on the book website in the file BoundedQueue2.java. The queue is managed in the usual circular fashion. Suppose we build an FSM where states are defined by the representation variables of BoundedQueue2. That is, a state is a 4-tuple defined by the values for [elements, size, front, back]. For example, the initial state has the value [[null, null], 0, 0, 0], and the state that results from pushing an object obj onto the queue in its initial state is [[obj, null], 1, 0, 1].

a) We do not care which specific objects are in the queue. Consequently, there are really just four useful values for the variable elements. What are they?
* [object, object]
* [null, null]
* [object, null]
* [null, object]

b) How many states are there?

There are: Element * size * back * front = 4 * 3 * 2 * 2 = 48 total states

c) How many of these states are reachable?

There are: 4 states reachable

d) Show the reachable states in a drawing.

4 reachable states:
* {[object, object], 2, object, object}
* {[null, null], 0, null, null}
* {[object, null], 1, object, null}
* {[null, object], 1, null, object}
