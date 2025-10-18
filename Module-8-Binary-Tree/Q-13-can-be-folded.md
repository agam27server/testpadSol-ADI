# Check if Binary Tree Can Be Folded

```java
class Result {
  static boolean solve(Node root1,Node root2){
      if(root1 == null && root2 == null){
          return true;
      }else if(root1 != null && root2 == null){
          return false;
      }else if(root1 == null && root2 != null){
          return false;
      }
      
      boolean left = solve(root1.left,root2.right);
      boolean right = solve(root1.right,root2.left);
      
      return right && left;
  }
  static int isFoldable(Node root) {
    // Write your code here
      
    if(solve(root,root)){
        return 1;
    }else{
        return 0;
    }
      
  }
}
```
