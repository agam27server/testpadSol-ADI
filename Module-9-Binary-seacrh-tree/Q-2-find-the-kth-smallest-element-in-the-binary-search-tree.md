# Find the Kth Smallest Element in the Binary Search Tree

```java
/* 
 *  class Node {
 *    int data;
 *    Node left; 
 *    Node right;
 *    public Node() {
 *      data = 0;
 *    }
 *    public Node(int d)  {
 *      data = d;
 *    }
 *  }
 *
 *  The above class defines a tree node.
 */
class Result {
  static void solve(Node root, List<Integer> list){
      if(root == null){
          return;
      }
      solve(root.left, list);
      list.add(root.data);
      solve(root.right, list);
  }
  static int kSmallest(Node root, int k) {
    // Write your code here
      if(root == null){
          return 0;
      }
      List<Integer> list = new ArrayList<>();
      solve(root,list);
      //inOrder(root);
      /*for(int i = 0; i < list.size(); i++){
          if(i == k-1){
              return list.get(i);
          }
      }*/
      return list.get(k-1);
  }
}
```
