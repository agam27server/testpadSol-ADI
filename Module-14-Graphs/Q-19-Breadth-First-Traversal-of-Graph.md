# Breadth First Traversal of Graph 
```java

void BFS(int startVertex) 
{ 
      boolean[] visited = new boolean[V];
      Queue<Integer> queue = new LinkedList<>();

      visited[startVertex] = true;
      queue.add(startVertex);

     
      while (!queue.isEmpty()) {
          int current = queue.poll();
          System.out.print(current + " ");

          // Visit all neighbors
          for (int neighbor : adjVertices.getOrDefault(current, new ArrayList<>())) {
              if (!visited[neighbor]) {
                  visited[neighbor] = true;
                  queue.add(neighbor);
              }
          }
      }
      System.out.println();
  }


```