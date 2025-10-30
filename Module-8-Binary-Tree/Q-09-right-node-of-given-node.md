# Find Right Sibling of Given Node

```java
class Result {
  static int findRightSibling(Node root, int key) {
    // Write your code here
      Queue<Node> q = new LinkedList<>();
      q.add(root);
      
      List<List<Integer>> res = new ArrayList<>();
      
      
      while(!q.isEmpty()){
          
          int size = q.size();
          List<Integer> temp = new ArrayList<>();
          
          for(int i = 0; i < size; i++){
              
              Node front = q.poll();
              temp.add(front.data);
              
              if(front.left != null){
                  q.add(front.left);
              }
              if(front.right != null){
                  q.add(front.right);
              }        
              
          }
          
          res.add(temp);
      }
    for(List<Integer> list : res){
        int ind = list.indexOf(key);
        if(ind != -1){
            if(ind == list.size()-1){
                return -1;
            }else{
                return list.get(ind+1);
            }
        }
    }
      return -1;
  }
}
```
