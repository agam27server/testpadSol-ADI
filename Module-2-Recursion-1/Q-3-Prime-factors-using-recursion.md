# Prime factors using recursion
```java
import java.util.Scanner;

class Main {
    public static void primeFactors(int num, int i) {
        if (num == 1)
            return;
        if (num % i == 0) {
            System.out.println(i);
            primeFactors(num / i, i);
        } else {
            primeFactors(num, i + 1);
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt();
        primeFactors(num, 2);
        sc.close();
    }
}
```