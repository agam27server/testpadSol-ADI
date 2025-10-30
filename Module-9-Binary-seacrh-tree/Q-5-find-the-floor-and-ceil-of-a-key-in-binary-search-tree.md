# Find the Floor and Ceil of a Key in Binary Search Tree

```java
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
  
  static int floorOf(Node root, int key) {
    int floor = -1;
    while (root != null) {
      if (root.data == key) {
        return root.data; // exact match
      } else if (root.data > key) {
        root = root.leftChild; // move left
      } else {
        floor = root.data;     // possible floor
        root = root.rightChild;
      }
    }
    return floor;
  }

  static int ceilOf(Node root, int key) {
    int ceil = -1;
    while (root != null) {
      if (root.data == key) {
        return root.data; // exact match
      } else if (root.data < key) {
        root = root.rightChild; // move right
      } else {
        ceil = root.data;       // possible ceil
        root = root.leftChild;
      }
    }
    return ceil;
  }
}
```
