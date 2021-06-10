### 4.1
Calc.java
```php
public class Calc {
    static public int add(int a, int b) {
        return a + b;
    }

    public static int subtract(int a, int b) {
        return a - b;
    }

    public static int multiply(int a, int b) {
        return a * b;
    }

    public static double divide(float a, float b) {
        return a / b;
    }
}
```
Test.java
```php
import org.junit.Test;
import static org.junit.Assert.*;

public class Test {
    Calc calc = new Calc();
    private int a = 1;
    private int b = 1;

    @Test
    public void testAdd() {
        assertEquals(calc.add(a, b), 2);
    }

    @Test
    public void testMinus() {
        assertEquals(calc.minus(a, b), 0);
    }

    @Test
    public void testMultiply() {
        assertEquals(calc.multiply(a, b), 1);
    }

    @Test
    public void testDivide() {
        assertEquals(calc.divide(a, b), 1);
    }
}
```
