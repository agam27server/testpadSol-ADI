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
  static void inor(Node root, List<Integer> list){
      if(root == null){
          return;
      }
      inor(root.left, list);
      list.add(root.data);
      inor(root.right, list);
  }
  static int kSmallest(Node root, int k) {
    // Write your code here
      if(root == null){
          return 0;
      }
      List<Integer> list = new ArrayList<>();
      inor(root, list);
      return list.get(k-1);
  }
```
