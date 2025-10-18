# Check if Binary Search Tree is Valid

```java
class Result {
  
  static void inorder(Node root,List<Integer> list){
      if(root == null){
          return;
      }
      inorder(root.left, list);
      list.add(root.data);
      inorder(root.right, list);
  }
  static int isBinarySearchTree(Node root) {
    // Write your code here
      if(root == null){
          return 1;
      }
      List<Integer> list = new ArrayList<>();
      inorder(root, list);
      
      for(int i = 1; i<list.size(); i++){
          if(list.get(i) < list.get(i-1)){
              return 0;
          }
      }
      return 1;
  }
}
```
