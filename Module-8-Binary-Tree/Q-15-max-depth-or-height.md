# Find Maximum Depth or Height of Binary Tree

```java
class Result {
  static int solve(Node root){
      
      //base case
      if(root == null){
          return 0;
      }
      
      int left = solve(root.left);
      int right = solve(root.right);
      
      return Math.max(left,right)+1;
  }
  static int treeHeight(Node root) {
    // Write your code here
    return solve(root)-1; //-1 as two node makes 1 edge
  }
}
```
