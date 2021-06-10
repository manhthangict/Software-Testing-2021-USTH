### 6.4.1 The restriction on interleaving next() and remove() calls is quite complex. The JUnit tests in IteratorTest.java only devote onetest for this situation, which may not be enough. Refine the input domain model with one or more additional characteristics to probe this behavior, and implement these tests in JUnit.

implement these tests
```php
import static org.junit.Assert.*;
import org.junit.*;
import java.util.*;

public class IteratorTest {
	
   private List<String> arr;      
   private Iterator<String> ite;   

   @Before public void setUp()  
   {
      arr = new ArrayList<String>();
      arr.add ("cat");
      arr.add ("dog");
      ite = arr.iterator();
   }
   
   // Tests for Iterator method next()
   // Test 1 of next(): testNext_BaseCase(): C1-T, C2-T, C5-T
    @Test public void testNext_BaseCase()
    {
        assertEquals ("cat", ite.next());
    }

    // Test 2 of next(): testNext_C1(): C1-F, C2-F, C5-T
    @Test(expected=NoSuchElementException.class)
    public void testNext_C1()
    {
        ite.next(); ite.next();        
        ite.next();                    
    }

    // Test 3 of next(): testNext_C2(): C1-T, C2-F, C5-T
    @Test public void testNext_C2()
    {
        arr = new ArrayList<String>();
        arr.add (null);
        ite = arr.iterator();
        assertNull (ite.next());
    }

    // Test 4 of next(): testNext_C5(): C1-T, C2-F, C5-F
    @Test(expected=ConcurrentModificationException.class)
    public void testNext_C5()
    {
        arr.add ("elephant");
        ite.next();
    }
```
```php
    // Tests for Iterator method remove()
// Test 1 of remove(): testRemove_BaseCase(): C1-T, C2-T, C3-T, C4-T, C5-T
    @Test public void testRemove_BaseCase()
    {
        ite.next();
        ite.remove();
        assertFalse (arr.contains ("cat"));
    }

    // Test 2 of remove(): testRemove_C1(): C1-F, C2-F, C3-T, C4-T, C5-T
    @Test public void testRemove_C1()
    {
        ite.next(); ite.next();        
        ite.remove();               
        assertFalse (arr.contains ("dog"));
    }

    // Test 3 of remove(): testRemove_C2(): C1-T, C2-F, C3-T, C4-T, C5-T
    @Test public void testRemove_C2()
    {
        arr.add (null);
        arr.add ("elephant");
        ite = arr.iterator();
        ite.next(); ite.next();     
        ite.next();       
        ite.remove();   
        assertFalse (arr.contains (null));
    }

    // Test 4 of remove(): testRemove_C3(): C1-T, C2-T, C3-F, C4-T, C5-T
    @Test(expected=UnsupportedOperationException.class)
    public void testRemove_C3()
    {
        arr = Collections.unmodifiableList (arr);
        ite = arr.iterator();
        ite.next();   
        ite.remove();
    }

    // Test 5 of remove(): testRemove_C4(): C1-T, C2-T, C3-T, C4-F, C5-T
    @Test (expected=IllegalStateException.class)
    public void testRemove_C4()
    {
        ite.remove();
    }


    // Test 6 of next(): testRemove_C5(): C1-T, C2-T, C3-T, C4-T, C5-F
    @Test (expected=ConcurrentModificationException.class)
    public void testRemove_C5()
    {
        ite.next();
        arr.add ("elephant");
        ite.remove();
    }
  ```
