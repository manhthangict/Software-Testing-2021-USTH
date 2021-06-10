#### 1.7: Consider the following three example classes. These are OO faults taken from Joshua Bloch’s Effective Java, Second Edition. Answer the following questions about each.

a)Explain what is wrong with the given code. Describe the fault precisely by proposing a modification to the code

BigDecimal equals require the values to be equal in value and scale, while BigDecimal compareTo only checks that the numbers are equal in value, not a scale.

b)If possible, give a test case that does not execute the fault. If not, briefly explain why not

A test case that does not execute the fault.

c)If possible, give a test case that executes the fault, but does notresult in an error state. If not, briefly explain why not

Test cases that execute the fault but don’t result an observable error.
