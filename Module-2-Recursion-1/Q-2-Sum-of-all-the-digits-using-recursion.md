# Sum of all the digits using recursion
```java
import java.util.Scanner;

class Main {
    // Recursive function to sum digits
    static int sumOfDigits(long n) {
        n = Math.abs(n);          // handle negative numbers
        if (n == 0) return 0;     // base case
        return (int)(n % 10 + sumOfDigits(n / 10)); // recursive step
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int k = sc.nextInt();      

        for (int i = 0; i < k; i++) {
            long n = sc.nextLong();
            int result = sumOfDigits(n);
            if(n<0){
               System.out.println(-result); 
            }
            else{
               System.out.println(result);
            }
        }
    }
}
```