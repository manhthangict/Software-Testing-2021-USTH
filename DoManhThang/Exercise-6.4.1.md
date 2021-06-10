### 6.4.1 The restriction on interleaving next() and remove() calls is quite complex. The JUnit tests in IteratorTest.java only devote onetest for this situation, which may not be enough. Refine the input domain model with one or more additional characteristics to probe this behavior, and implement these tests in JUnit

The following characteristics have been identified and are used to generate tests for the methods:
```php
import static org.junit.Assert.*;
import org.junit.*;
import java.util.*;

public class IteratorTest {
	
   private List<String> lst;      
   private Iterator<String> itr;   

   @Before public void setUp()  
   {
      lst = new ArrayList<String>();
      lst.add ("cat");
      lst.add ("dog");
      itr = lst.iterator();
   }
```
Iterator method next()
```php
 // C1-T, C2-T, C3-T, C4-T, C5-T
   @Test public void testRemove_BaseCase()
   {
      itg.next();
      itg.remove();
      assertFalse (lst.contains ("cat"));
   }
   
   // C1-F, C2-F, C3-T, C4-T, C5-T
   @Test public void testRemove_C1()
   {
      itg.next(); itg.next();        // consume the cat and the dog
      itg.remove();                  // remove dog from list.
      assertFalse (lst.contains ("dog"));
   }
   
   // C1-T, C2-F, C3-T, C4-T, C5-T
   @Test public void testRemove_C2()
   {
      lst.add (null);
      lst.add ("elephant");
      itg = lst.iterator();
      itg.next(); itg.next();        // consume the cat and the dog
      itg.next();        // consume null; iterator not empty
      itg.remove();      // remove null from list
      assertFalse (lst.contains (null));
   }
   
   // C1-T, C2-T, C3-F, C4-T, C5-T
   @Test(expected=UnsupportedOperationException.class)
   public void testRemove_C3()
   {
      lst = Collections.unmodifiableList (lst);
      itg = lst.iterator();
      itg.next();   // consume first element to make C4 true
      itg.remove();
   }
   
   // C1-T, C2-T, C3-T, C4-F, C5-T
   @Test (expected=IllegalStateException.class)
   public void testRemove_C4()
   {
      itg.remove();
   }
      
      
   // C1-T, C2-T, C3-T, C4-T, C5-F
   @Test (expected=ConcurrentModificationException.class)
   public void testRemove_C5()
   {
      itg.next();
      lst.add ("elephant");
      itg.remove();
   }
   ```
   next() method
   ```php
    @Test public void testNext_BaseCase()
    {
        assertEquals ("cat", itg.next());
    }

    // Test 2 of next(): testNext_C1(): C1-F, C2-F, C5-T
    @Test(expected=NoSuchElementException.class)
    public void testNext_C1()
    {
        itg.next(); 
		itg.next();        
        itg.next();                  
    }

    // Test 3 of next(): testNext_C2(): C1-T, C2-F, C5-T
    @Test public void testNext_C2()
    {
        lst = new ArrayList<String>();
        lst.add (null);
        itg = lst.iterator();
        assertNull (itg.next());
    }

    // Test 4 of next(): testNext_C5(): C1-T, C2-F, C5-F
    @Test(expected=ConcurrentModificationException.class)
    public void testNext_C5()
    {
        lst.add ("elephant");
        itg.next();
    }
    ```
   
   
