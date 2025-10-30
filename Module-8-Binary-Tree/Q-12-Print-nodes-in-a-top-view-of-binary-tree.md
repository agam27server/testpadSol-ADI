# Print nodes in a top view of Binary Tree
```java
import java.util.*;

// Class containing the solution logic
class Result {

  static void printTopView(Node root) {
    if (root == null)
      return;

    // Map to store the first node at every horizontal distance (HD)
    TreeMap<Integer, Integer> topView = new TreeMap<>();

    // Queue for level order traversal: stores node + its horizontal distance
    Queue<Pair> queue = new LinkedList<>();

    queue.add(new Pair(root, 0)); // root has horizontal distance 0

    while (!queue.isEmpty()) {
      Pair p = queue.poll();
      Node curr = p.node;
      int hd = p.hd;

      // If this HD is not already present in map, add it
      if (!topView.containsKey(hd)) {
        topView.put(hd, curr.data);
      }

      // Add left and right children with updated HD
      if (curr.left != null)
        queue.add(new Pair(curr.left, hd - 1));
      if (curr.right != null)
        queue.add(new Pair(curr.right, hd + 1));
    }

    // Print all entries in map (sorted by HD)
    for (int val : topView.values())
      System.out.print(val + " ");
  }
}

// Helper class for queue (Node + horizontal distance)
class Pair {
  Node node;
  int hd;

  Pair(Node n, int h) {
    node = n;
    hd = h;
  }
}
```

