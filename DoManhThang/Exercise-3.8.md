### 3.8 Develop a set of data-driven JUnit tests for the Min program. Thesetests should be for normal, not exceptional, returns.
```php
import java.util.*;

 
public class Ex3
{
    public static <T extends Comparable<? super T>> T min (List<? extends T> list)
    {
       if (list.size() == 0)
       {
          throw new IllegalArgumentException ("Min.min");
       }

 
       Iterator<? extends T> itr = list.iterator();
       T result = itr.next();

 
       if (result == null) throw new NullPointerException ("Min.min");

 
       while (itr.hasNext())
           T comp = itr.next();
           if (comp.compareTo (result) < 0)
           {
               result = comp;
           }
       }
       return result;
    }
}
```
