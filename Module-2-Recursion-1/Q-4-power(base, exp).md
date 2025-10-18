# power(base, exp) - using recursion
```java
class Result {
    static int power(int base, int exp) {
        //Base Case
        if (exp == 0) return 1;                   
        if (exp > 0) return base * power(base, exp - 1);   // positive exponent
        return -1;       // for negative exponent the result has to be -1
    }
}
```