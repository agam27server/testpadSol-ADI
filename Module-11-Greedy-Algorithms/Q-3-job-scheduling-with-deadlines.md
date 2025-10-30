# Job Scheduling with Deadlines

```java
class Result {
  static int jobScheduling(int[] deadlines, int[] profits) {
    // Write your code here
      int maxdeadline = -1;
      int maxProfit = 0;
      for(int i = 0; i < deadlines.length;i++){
          maxdeadline = Math.max(maxdeadline,deadlines[i]);
      }
      int[] deadlineArr = new int[maxdeadline];
      List<int[]> jobs = new ArrayList<>();
      for(int i = 0; i < deadlines.length;i++){
            jobs.add(new int[]{deadlines[i],profits[i]});
        }
      jobs.sort((a,b) -> b[1]-a[1]);
      for(int[] job : jobs){
          int deadline = job[0]-1;
          for(int i = deadline; i >= 0; i--){
              if(deadlineArr[i] == 0){
                  maxProfit += job[1];
                  deadlineArr[i] = 1;
                  break;
              }
          }
      }
      return maxProfit;
  }
}
```
