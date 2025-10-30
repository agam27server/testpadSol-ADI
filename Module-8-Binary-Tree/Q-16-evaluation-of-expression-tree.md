/* class Node {
  int data; // data used as key value
  Node leftChild;
  Node rightChild;
  public Node()  {
    data = 0;
  }
  public Node(int d)  {
    data = d;
  }
} */

class Result {
  static int evaluateTree(Node t1) {
    // Base case: if node is null
    if (t1 == null)
      return 0;

    // If leaf node, return the value directly
    if (t1.leftChild == null && t1.rightChild == null)
      return t1.data;

    // Recursively evaluate left and right subtrees
    int leftVal = evaluateTree(t1.leftChild);
    int rightVal = evaluateTree(t1.rightChild);

    // Apply the operator based on ASCII code
    switch (t1.data) {
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
