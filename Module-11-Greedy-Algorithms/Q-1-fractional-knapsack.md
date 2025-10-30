# Fractional Knapsack

```java
import java.util.*;
class Result
{
  static double fractionalKnapsack(int val[], int weight[], int n, int capacity)
  {
      double[][] items = new double[n][3];
      // Store value, weight, and value/weight ratio
      for (int i = 0; i < n; i++) {
          items[i][0] = val[i];
          items[i][1] = weight[i];
          items[i][2] = (double)val[i] / weight[i];
      }
      // Sort items by ratio (descending)
      Arrays.sort(items, (a, b) -> Double.compare(b[2], a[2]));
      double totalValue = 0.0;
      int currentWeight = 0;
      // Greedy selection
      for (int i = 0; i < n; i++) {
          if (currentWeight + items[i][1] <= capacity) {
              totalValue += items[i][0];
              currentWeight += items[i][1];
          } else {
              int remain = capacity - currentWeight;
              totalValue += items[i][0] * ((double)remain / items[i][1]);
              break;
          }
      }
      return totalValue;
  }
}
```
