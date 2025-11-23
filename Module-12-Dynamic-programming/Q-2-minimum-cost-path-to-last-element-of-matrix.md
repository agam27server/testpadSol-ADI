# Minimum Cost Path to Last Element of Matrix

```java
class Result {
    static int solve(int[][] cost, int m, int n, int i, int j, int[][] memo) {
        // base case: destination
        if (i == m - 1 && j == n - 1)
            return cost[i][j];
        // out of bounds
        if (i >= m || j >= n)
            return Integer.MAX_VALUE;
        // if already computed
        if (memo[i][j] != -1)
            return memo[i][j];
        // explore 3 directions
        int down = solve(cost, m, n, i + 1, j, memo);
        int right = solve(cost, m, n, i, j + 1, memo);
        int diag = solve(cost, m, n, i + 1, j + 1, memo);
        // store & return
        memo[i][j] = cost[i][j] + Math.min(down, Math.min(right, diag));
        return memo[i][j];
    }
    static int minCostPath(int[][] cost, int m, int n) {
        if (m == 0 || n == 0) return 0;
        int[][] memo = new int[m][n];
        for (int[] row : memo) Arrays.fill(row, -1);
        return solve(cost, m, n, 0, 0, memo);
    }
}
```
