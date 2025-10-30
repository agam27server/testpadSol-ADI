# Binary Tree Traversals
## Inorder Preorder Postorder 

```java
static void inorder(Node root)
{
    if(root == null){
        return;
    }
    
    // Traverse left subtree
    inorder(root.leftChild);
    System.out.print(root.data + " ");
    // Traverse right subtree
    inorder(root.rightChild);
}

static void preorder(Node root)
{
    if(root == null){
        return;
    }
    
    System.out.print(root.data + " ");
    // Traverse left subtree
    preorder(root.leftChild);
    // Traverse right subtree
    preorder(root.rightChild);
}

static void postorder(Node root)
{
    if(root == null){
        return;
    }
    
    // Traverse left subtree
    postorder(root.leftChild);
    // Traverse right subtree
    postorder(root.rightChild);
    System.out.print(root.data + " ");
}
```