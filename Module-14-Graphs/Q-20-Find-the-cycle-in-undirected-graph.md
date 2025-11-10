# Find the cycle in undirected graph
```java
import java.util.*;
class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int vx = sc.nextInt(); // number of vertices
        int e = sc.nextInt();  // number of edges
        int[][] edges = new int[e][2];
        for (int i = 0; i < e; i++) {
            edges[i][0] = sc.nextInt();
            edges[i][1] = sc.nextInt();
        }
        Map<Integer, List<Integer>> map = new HashMap<>();
        for (int[] edge : edges) {
            int u = edge[0];
            int v = edge[1];
            map.putIfAbsent(u, new ArrayList<>());
            map.putIfAbsent(v, new ArrayList<>());
            map.get(u).add(v);
            map.get(v).add(u);
        }
        boolean[] visited = new boolean[vx];
        boolean flag = false;
        for (int i = 0; i < vx; i++) {
            if (!visited[i]) {
                if (dfs(i, -1, visited, map)) {
                    flag = true;
                    break;
                }
            }
        }
        System.out.println(flag ? "Yes" : "No");
    }
    public static boolean dfs(int node, int parent, boolean[] visited, Map<Integer, List<Integer>> map) {
        visited[node] = true;
        for (int neigh : map.get(node)) {
            if (!visited[neigh]) {
                if (dfs(neigh, node, visited, map)) return true;
            } else if (neigh != parent) {
                return true;
            }
        }
        return false;
    }
}
```