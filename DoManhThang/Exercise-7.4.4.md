### 7.4.4 Use the following methods trash() and takeOut() to answer questions a–c.
```php
/* 1 */public static void trash (int x)    
/* 2 */{                         
/* 3 */   int m, n;                 
/* 4 */   m = 0;                    
/* 5 */   if (x > 0)               
/* 6 */      m = 4;                
/* 7 */   if (x > 5)              
/* 8 */      n = 3*m;              
/* 9 */   else                     
/*10 */      n = 4*m;             
/*11 */   int o = takeOut (m, n);
/*12 */   System.out.println ("o is: " + o);  
/*13 */}
/*14 */public static int takeOut (int a, int b)
/*15 */{
/*16 */   int d, e;
/*17 */
/*18 */   d = 42*a;
/*19 */   if (a > 0)
/*20 */      e = 2*b+d;
/*21 */   else
/*22 */      e = b+d;
/*23 */   return (e);
/*24 */}
```

a) Give all call sites using the line numbers given

For variable m, lines are 3, 4, 6, 8, 10, 11

For variable n, lines are 3, 8, 10, 11

b) Give all pairs of last-defs and first-uses

For variable m, last def is in line 6, first use is in line 8

For variable n, last def is in line 10, first use is in line 20

c) Provide test inputs that satisfy all-coupling-uses

  x = 1   x = 6     x = 0
