# Convert Level Order Traversal to BST

```java
/* class Node {
  int data; // data used as key value
  Node leftChild;
  Node rightChild;
  public Node()  {
    data=0;  }
  public Node(int d)  {
    data=d;  }
 } Above class is declared for use. */
class Result {
  static Node insert(Node root, int val) {
        if (root == null) {
            return new Node(val);
        }
        if (val < root.data) {
            root.leftChild = insert(root.leftChild, val);
        } else {
            root.rightChild = insert(root.rightChild, val);
        }
        return root;
    }
    // Function to build BST from level order traversal
    static Node buildSearchTree(int arr[], int n) {
        if (n == 0) return null;
        Node root = null;
        for (int i = 0; i < n; i++) {
            root = insert(root, arr[i]);
        }
        return root;
    }
}
```
