# Find Lowest Common Ancestor

```java
class Result {
    static Node solve(Node root, int k1, int k2){
        //base case
        if(root == null){
            return null;
        }
        
        //return if found
        if(root.data == k2) return root;
        if(root.data == k1) return root;
        
        //left and right ki call
        Node left = solve(root.left, k1, k2);
        Node right = solve(root.right, k1, k2);
        
        
        if(left != null && right != null){
            return root; //agar left right dono sides se ans aaaye 
        }else if(left != null || right == null){
            return left; //agar left se aaaye aur right se kuch na aaye
        }else if(right != null || left == null){
            return right; //agar right se aaye left se na aaye
        }else{ //agar left right dono se null aaye
            return null;
        }
    }
  static int lowestCommonAncestor(Node root, int k1, int k2) {
    // Write your code here
      if(root == null){
          return -1;
      }
      
      //rec func call
      Node res = solve(root, k1, k2);
      
      return res.data;
    
  }
}
```
