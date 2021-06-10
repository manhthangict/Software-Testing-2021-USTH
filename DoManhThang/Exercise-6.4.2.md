### 6.4.2 It is possible to modify an ArrayList without using the remove() method and yet have a subsequent call to remove() fail to throw ConcurrentModificationException. Develop a (failing) JUnit test that exhibits this behavior.

```php
import org.junit.*;
import java.util.*;
import static org.junit.Assert.*;

public class failingTest {
    private List<String> arr;
    private Iterator<String> ite;

    @Test (expected=ConcurrentModificationException.class)
    public void testRemove() {
        arr = new ArrayList<String>();
        arr.add ("manh");
        arr.add ("thang");
        ite = arr.iterator();
        ite.next();
        arr.add("something");
        ite.remove();
    }
}
```
