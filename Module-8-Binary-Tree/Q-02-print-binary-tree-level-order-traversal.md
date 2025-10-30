# Print Binary Tree - Level Order Traversal

```java
static void printLevelWise(Node root) {
        if (root == null) return;

        Queue<Node> q = new LinkedList<>();
        q.add(root);

        while (!q.isEmpty()) {
            int size = q.size();

            for (int i = 0; i < size; i++) {
                Node front = q.poll();
                
                if (front.left != null) q.add(front.left);
                if (front.right != null) q.add(front.right);
                if(i == size-1){
                    System.out.print(front.data);
                }else{
                    System.out.print(front.data + " ");
                }
            }
            System.out.println();
        }
}
```
