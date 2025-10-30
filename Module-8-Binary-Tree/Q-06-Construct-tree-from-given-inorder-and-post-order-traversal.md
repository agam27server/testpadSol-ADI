# Construct tree from given inorder and post order traversal
```java
/*
class Node {
    int data;
    Node leftChild;
    Node rightChild;
    public Node(int d) {
        data = d;
    }
}
*/

class Result {
    static int postIndex;

    static Node buildTree(int in[], int post[], int N) {
        postIndex = N - 1; 
        return Solve(in, post, 0, N - 1);
    }

    static Node Solve(int in[], int post[], int start, int end) {
        if (start > end)
            return null;

        Node node = new Node(post[postIndex--]); 
        
        if (start == end)
            return node;


        int inIndex = search(in, start, end, node.data);

        
        node.rightChild = Solve(in, post, inIndex + 1, end);
        node.leftChild = Solve(in, post, start, inIndex - 1);

        return node;
    }

    static int search(int[] in, int start, int end, int value) {
        for (int i = start; i <= end; i++) {
            if (in[i] == value)
                return i;
        }
        return -1; // Should not happen if inputs are valid
    }
}
```