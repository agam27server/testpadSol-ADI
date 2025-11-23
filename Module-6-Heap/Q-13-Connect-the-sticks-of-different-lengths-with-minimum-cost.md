# Connect the sticks of different lengths with minimum cost

```java
import java.util.*;

class Result {

    static int sum(PriorityQueue<Integer> heap){
        int total = 0;

        while (heap.size() > 1) {
            int temp1 = heap.poll();
            int temp2 = heap.poll();

            int cost = temp1 + temp2;
            total += cost;

            heap.add(cost);
        }
        return total;
    }

    static int connectCost(int lengths[], int n){
        PriorityQueue<Integer> heap = new PriorityQueue<>();

        for (int x : lengths) {
            heap.add(x);
        }

        return sum(heap);
    }
}
```