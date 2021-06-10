### 7.5.2 
```
partOfDay : {Wake, Sleep}
temp : {Low, High}

// Initially "Wake" at "Low" temperature

// Effects: Advance to next part of day
public void advance();

// Effects: Make current temp higher, if possible
public void up();

// Effects: Make current temp lower, if possible
public void down();
```

a) How many states are there?

{wake, low} {wake, high} {sleep, low} {sleep, high}

b) Draw and label the states (with variable values) and transitions (with method names). Notice that all of the methods are total, that is, their behaviors are defined for all possible inputs

```
(sleep, low)    -> advance()    -> (wake, low)
(sleep, low)    -> up           -> (sleep, high)
(sleep, high)   -> advance()    -> (wake, high)
(sleep, high)   -> down()       -> (sleep, low)
(wake, low)     -> advance()    -> (sleep, low)
(wake, low)     -> up()         -> (wake, high)
(wake, high)    -> advance()    -> (sleep, high)
(wake, high)    -> down()       -> (wake, low)
```
c) A test case is simply a sequence of method calls. Provide a test set that satisfies Edge Coverage on your graph

[1,3] [1,2] [1,4] [2,4] [2,3] [2,1] [3,1] [3,4] [3,2] [4,2] [4,1] [4,3]
