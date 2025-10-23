```java
// Do not change the class name
class Result {

    // Helper function to check if the cell is valid and not visited
    private static boolean isSafe(int x, int y, boolean[][] visited, int m, int n) {
        return (x >= 0 && x < m && y >= 0 && y < n && !visited[x][y]);
    }

    // DFS function to count occurrences of the word starting at (i,j)
    private static int solve(char[][] board, String word, int i, int j, int index, boolean[][] visited, int m, int n) {
        if (board[i][j] != word.charAt(index)) return 0;

        if (index == word.length() - 1) return 1; // last character matched

        visited[i][j] = true;
        int total = 0;

        // Explore four directions manually
        if (isSafe(i, j + 1, visited, m, n)) total += solve(board, word, i, j + 1, index + 1, visited, m, n); // right
        if (isSafe(i, j - 1, visited, m, n)) total += solve(board, word, i, j - 1, index + 1, visited, m, n); // left
        if (isSafe(i - 1, j, visited, m, n)) total += solve(board, word, i - 1, j, index + 1, visited, m, n); // up
        if (isSafe(i + 1, j, visited, m, n)) total += solve(board, word, i + 1, j, index + 1, visited, m, n); // down

        visited[i][j] = false; // backtrack
        return total;
    }

    /* 
     * Complete the below function.
     * Return the count of word in the 2-D board
     */
    static int countWord(char board[][], String word, int m, int n) {
        int count = 0;
        boolean[][] visited = new boolean[m][n];

        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                count += solve(board, word, i, j, 0, visited, m, n);
            }
        }
        return count;
    }
}
```
