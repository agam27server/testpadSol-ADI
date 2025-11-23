# The Subset Sum Problem

```java
class Result
{
  static boolean solve(int a[], int n, int sum, int i){
      if(sum == 0){
          return true;
      }
      if(sum < 0 || i > n){
          return false;
      }
      boolean include = solve(a,n,sum-a[i],i+1);
      boolean exclude = solve(a,n,sum,i+1);
      return include || exclude;
  }
  static int subsetSum(int a[], int n, int sum){
    // Write your code here
      return solve(a,n,sum,0)? 1 : 0;
  }
}
```
