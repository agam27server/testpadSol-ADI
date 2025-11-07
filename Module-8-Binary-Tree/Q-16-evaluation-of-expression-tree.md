# Evaluation of expression tree
```java
/* class Node {
  int data; // data used as key value
  Node leftChild;
  Node rightChild;
  public Node()  {
    data=0;  
  }
  public Node(int d)  {
    data=d;  
  }
 } 
*/

class Result {
  static int evaluateTree(Node root) {
    if (root == null)
      return 0;

    // If leaf node, return the operand value
    if (root.leftChild == null && root.rightChild == null)
      return root.data;

    // Evaluate left and right subtrees
    int leftVal = evaluateTree(root.leftChild);
    int rightVal = evaluateTree(root.rightChild);

    // Operator node: data stores ASCII of operator
    switch (root.data) {
      case 43: // '+'
        return leftVal + rightVal;
      case 45: // '-'
        return leftVal - rightVal;
      case 42: // '*'
        return leftVal * rightVal;
      case 47: // '/'
        return leftVal / rightVal;
      default:
        return 0;
    }
  }
}
```