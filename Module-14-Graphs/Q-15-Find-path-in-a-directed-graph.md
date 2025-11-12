# Find path in a directed graph
```java 
import java.util.*;

class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int V = sc.nextInt(); 
        int E = sc.nextInt(); 

        ArrayList<ArrayList<Integer>> adj = new ArrayList<>(V);
        for (int i = 0; i < V; i++)
            adj.add(new ArrayList<>());

        for (int i = 0; i < E; i++) {
            int u = sc.nextInt();
            int v = sc.nextInt();
            adj.get(u).add(v); // directed edge u -> v
        }

        int src = sc.nextInt();
        int dest = sc.nextInt();

        if (pathExists(adj, V, src, dest))
            System.out.println("YES");
        else
            System.out.println("NO");
    }

        static boolean pathExists(ArrayList<ArrayList<Integer>> adj, int V, int src, int dest) {
        boolean[] visited = new boolean[V];
        Queue<Integer> q = new LinkedList<>();

        q.add(src);
        visited[src] = true;

        while (!q.isEmpty()) {
            int node = q.poll();

            if (node == dest)
                return true;

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    q.add(neighbor);
                }
            }
        }
        return false;
    }
}

```