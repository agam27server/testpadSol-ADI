# Factorial using recursion
```java
class Result{
 static int factorial(int n) {
    //Base Case
    if(n==1 || n==0 ){
        return 1;
    }
    return n*factorial(n-1);
  }
}
```