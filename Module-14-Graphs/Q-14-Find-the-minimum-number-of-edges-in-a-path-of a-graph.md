# Find the minimum number of edges in a path of a graph 
```java
class Result {
  static int number_of_edges(int n) {
    if (n == 1) return 0; 

    Queue<Integer> queue = new LinkedList<>();
    boolean[] visited = new boolean[n + 1];
    int[] dist = new int[n + 1];

    queue.add(1);
    visited[1] = true;
    dist[1] = 0;

    while (!queue.isEmpty()) {
      int curr = queue.poll();

      // If we reach n, return distance
      if (curr == n)
        return dist[curr];

      // Possible next nodes
      int next1 = curr + 1;
      int next2 = curr * 3;

      if (next1 <= n && !visited[next1]) {
        visited[next1] = true;
        dist[next1] = dist[curr] + 1;
        queue.add(next1);
      }

      if (next2 <= n && !visited[next2]) {
        visited[next2] = true;
        dist[next2] = dist[curr] + 1;
        queue.add(next2);
      }
    }

    return -1; 
  }
}
```