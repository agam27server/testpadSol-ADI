# Shortest path in a binary maze
```java
import java.util.*;
class Result {
    static class Pair {
        int row, col, dist;
        Pair(int row, int col, int dist) {
            this.row = row;
            this.col = col;
            this.dist = dist;
        }
    }
    static int shortestPath(int mat[][], int srcR, int srcC, int destR, int destC, int m, int n) {
        if (mat[srcR][srcC] == 0 || mat[destR][destC] == 0)
            return -1;
        int[] dr = {-1, 0, 1, 0};
        int[] dc = {0, 1, 0, -1};
        boolean[][] visited = new boolean[m][n];
        Queue<Pair> q = new LinkedList<>();
        // Start from the source
        q.add(new Pair(srcR, srcC, 0));
        visited[srcR][srcC] = true;
        while (!q.isEmpty()) {
            Pair p = q.poll();
            if (p.row == destR && p.col == destC)
                return p.dist;
            for (int i = 0; i < 4; i++) {
                int newR = p.row + dr[i];
                int newC = p.col + dc[i];
                if (newR >= 0 && newR < m && newC >= 0 && newC < n &&
                    mat[newR][newC] == 1 && !visited[newR][newC]) {
                    visited[newR][newC] = true;
                    q.add(new Pair(newR, newC, p.dist + 1));
                }
            }
        }
        return -1;
    }
}
```