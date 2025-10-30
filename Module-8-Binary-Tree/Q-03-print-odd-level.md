# Print Odd Level Nodes

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
  static void printOdd(Node root) {
    // Write your code here
      if(root == null){
          return;
      }
      int level = 1;
      
      Queue<Node> q = new LinkedList<>();
      q.add(root);
      
      while(!q.isEmpty()){
          int size = q.size();

          for(int i = 0; i < size; i++){
              Node front = q.poll();
              if(front.left != null){
                  q.add(front.left);
              }
              
              if(front.right != null){
                  q.add(front.right);
              }
              
              if(level%2 != 0){
                  System.out.print(front.data + " ");
              }
          }
          level++;
      }
  }
}
```
