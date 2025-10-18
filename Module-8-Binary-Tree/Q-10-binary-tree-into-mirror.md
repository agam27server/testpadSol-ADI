# Convert Binary Tree into Mirror

```java
static Node solve(Node root) {
    if (root == null) {
        return null;
    }

    Node newNode = new Node(root.data);

    newNode.left = solve(root.right);
    newNode.right = solve(root.left);

    return newNode;
}

static Node findMirror(Node root) {
    if (root == null) {
        return null;
    }
    return solve(root);
}
```
