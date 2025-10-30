# Interval Scheduling Problem

```java
class Result {
  static int intervalScheduling(int[] start, int[] end) {
    // Write your code here
      List<int[]> intervals = new ArrayList<>();
      int n = start.length;
      for(int i = 0; i < n; i++){
          intervals.add(new int[]{start[i],end[i]});
      }
      //sorting
      intervals.sort((a,b)->a[1]-b[1]);
      int endInterval = -1;
      int maxIntervals = 0;
      for(int[] interval : intervals){
          int s = interval[0];
          int e = interval[1];
          if(endInterval <= s){
              maxIntervals++;
              endInterval = e;
          }
      }
      return maxIntervals;
  }
}
```
