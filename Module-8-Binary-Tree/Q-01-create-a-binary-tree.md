# Create a Binary Tree - Level Order Traversal

```java
static Node buildTree(int arr[], int n) {
    if(arr.length == 0)return null;
    int ptr =1;
    Node root = new Node(arr[0]);
    Queue<Node> q = new LinkedList<>();
    q.add(root);
    while(ptr< arr.length){
        int size = q.size();
        for (int i=0;i< size;i++){
            Node temp = q.poll();
            if(ptr<arr.length){
                temp.left = new Node(arr[ptr]);
                q.add(temp.left);
            }
            ptr++;
            if(ptr<arr.length){
                temp.right = new Node(arr[ptr]);
                q.add(temp.right);
            }
            ptr++;
        }
    }
    return root;
}
```
