### 7.5.2 For the following questions a–c, consider the FSM that models a (simplified) programmable thermostat. Suppose the variables that define the state and the methods that transition between states are:
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

There are 4 states: [wake, low] [wake, high] [sleep, low] [sleep, high]

b) Draw and label the states (with variable values) and transitions (with method names)
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
c) A test case is simply a sequence of method calls. Provide a test set that satisfies Edge Coverage on your graph. 

The test set T: [1,3] [1,2] [1,4] [2,4] [2,3] [2,1] [3,1] [3,4] [3,2] [4,2] [4,1] [4,3]
