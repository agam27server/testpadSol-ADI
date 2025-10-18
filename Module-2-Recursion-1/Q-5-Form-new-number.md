# Form a new number using even number of digits from the number
```java
import java.util.Scanner;

class Main {
       static int evenDigits(int n) {
        // Handle negative numbers
        if (n < 0) return -evenDigits(-n);

        //Base Case
        if (n == 0) return 0;

        int last = n % 10;
        int rest = evenDigits(n / 10);

        if (last % 2 == 0) {
            return rest * 10 + last;  // append even digit
        } else {
            return rest;               // skip odd digit
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt(); 

        for (int i = 0; i < t; i++) {
            int num = sc.nextInt();        
            int newnum = evenDigits(num);  
            System.out.println(newnum);
        }
    }
}
```