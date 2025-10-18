# Check if Two Trees are Identical

```java
class Result {
    
  static boolean solve(Node t1, Node t2){
      
       if(t1 == null && t2 == null){
           return true;
       }else if(t1 != null && t2 == null){
           return false;
       }else if(t1 == null && t2 != null){
           return false;
       }else if(t1.data != t2.data){
           return false;
       }
      
      boolean left = solve(t1.left,t2.left);
      boolean right = solve(t1.right,t2.right);
      
      return left && right;
   }
  static int areSameTree(Node t1, Node t2) {
    // Write your code here
      
      if(solve(t1,t2)){
          return 1;
      }else{
          return 0;
      }
    
  }
}
```
