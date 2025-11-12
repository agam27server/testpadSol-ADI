# Depth First Traversal of Graph
```java
void DFSUtil(int v, boolean visited[]) 
{ 
    visited[v] = true; 
    System.out.print(v + " "); 
  
    List<Integer> neighbors = adjVertices.getOrDefault(v, new ArrayList<>());
    for (int n : neighbors) { 
        if (!visited[n]) 
            DFSUtil(n, visited); 
    } 
} 

void DFS(int v) 
{ 
 
    int totalVertices = adjVertices.size();
    boolean visited[] = new boolean[totalVertices]; 


    DFSUtil(v, visited); 
    System.out.println();
} 

```