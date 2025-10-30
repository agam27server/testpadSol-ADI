# Print cousins of a given node in Binary Tree 
```java
import java.util.*;

class Result {

    // Function to print cousins of a given key node
    public static void printCousins(Node root, int key) {
        if (root == null || root.data == key) {
            System.out.println("-1");
            return;
        }

        Queue<Node> queue = new LinkedList<>();
        queue.add(root);
        boolean found = false;

        while (!queue.isEmpty() && !found) {
            int size = queue.size();

            // Process one level at a time
            for (int i = 0; i < size; i++) {
                Node current = queue.poll();

                // Check if this node is parent of the key
                if ((current.leftChild != null && current.leftChild.data == key) ||
                    (current.rightChild != null && current.rightChild.data == key)) {
                    found = true; // We found the parent, next level are cousins
                } else {
                    // Add children to queue if they are not the parent of key
                    if (current.leftChild != null)
                        queue.add(current.leftChild);
                    if (current.rightChild != null)
                        queue.add(current.rightChild);
                }
            }
        }

        // If queue is empty => no cousins
        if (queue.isEmpty()) {
            System.out.println("-1");
            return;
        }

        // Print all nodes currently in queue (the cousins)
        while (!queue.isEmpty()) {
            System.out.print(queue.poll().data + " ");
        }
        System.out.println();
    }
}
```