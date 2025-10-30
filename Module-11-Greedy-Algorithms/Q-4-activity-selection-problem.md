# Activity Selection Problem

```java
class Result {
  // Print the starting time of selected activities in sorted order separated by space
  static void activitySelection(int[] start, int[] finish) {
    // Write your code here
      List<int[]> activities = new ArrayList<>();
      List<Integer> res = new ArrayList<>();
      for(int i = 0; i < start.length; i++){
         activities.add(new int[]{start[i],finish[i]});
      }
      activities.sort((a,b)->a[1]-b[1]);
      int last = -1;
      for(int[] act: activities){
          if(act[0] >= last){
              res.add(act[0]);
              //System.out.println("setting last "+act[1]);
              last = act[1];
          }
      }
      Collections.sort(res);
      for(int i : res){
          System.out.print(i + " ");
      }
  }
}
```
