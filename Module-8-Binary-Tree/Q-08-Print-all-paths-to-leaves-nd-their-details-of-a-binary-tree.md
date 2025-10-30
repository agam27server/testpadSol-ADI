# Print All Paths to Leaves and Their Details

```java
static void solve(Node root, List<Integer> temp, List<List<Integer>> res) {
    if (root == null) {
        return;
    }

    temp.add(root.data);

    if (root.left == null && root.right == null) {
        res.add(new ArrayList<>(temp)); 
    } else {
        solve(root.left, temp, res);
        solve(root.right, temp, res);
    }

    temp.remove(temp.size() - 1); 
}

static void printAllPaths(Node root) {
      if(root == null){
          return;
      }
        List<List<Integer>> res = new ArrayList<>();
      List<Integer> temp = new ArrayList<>();
      solve(root, temp, res);
      
      for (List<Integer> path : res) {
        for (int val : path) {
            System.out.print(val + " ");
        }
        System.out.println(path.size()-1); 
    }
      System.out.println(res.size());
}
```
