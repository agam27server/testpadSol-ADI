# Solve Sudoku

```java
import java.util.*;

class Result {
    static final int N = 9;

    static boolean isSafe(int[][] mat, int row, int col, int num) {
        // Check row and column
        for (int i = 0; i < N; i++) {
            if (mat[row][i] == num || mat[i][col] == num)
                return false;
        }

        // Check 3x3 subgrid
        int startRow = row - row % 3;
        int startCol = col - col % 3;
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                if (mat[startRow + i][startCol + j] == num)
                    return false;
            }
        }
        return true;
    }

    static boolean solveSudokuUtil(int[][] mat) {
        for (int row = 0; row < N; row++) {
            for (int col = 0; col < N; col++) {
                if (mat[row][col] == 0) {
                    for (int num = 1; num <= 9; num++) {
                        if (isSafe(mat, row, col, num)) {
                            mat[row][col] = num;
                            if (solveSudokuUtil(mat))
                                return true;
                            mat[row][col] = 0; // backtrack
                        }
                    }
                    return false; // no valid number fits here
                }
            }
        }
        return true; // solved
    }

    static boolean isValidSudoku(int[][] mat) {
        // Check no duplicates in rows, cols, and boxes
        boolean[][] rowCheck = new boolean[N][N + 1];
        boolean[][] colCheck = new boolean[N][N + 1];
        boolean[][] boxCheck = new boolean[N][N + 1];

        for (int r = 0; r < N; r++) {
            for (int c = 0; c < N; c++) {
                int num = mat[r][c];
                if (num == 0) continue;
                int boxIndex = (r / 3) * 3 + (c / 3);
                if (rowCheck[r][num] || colCheck[c][num] || boxCheck[boxIndex][num])
                    return false;
                rowCheck[r][num] = colCheck[c][num] = boxCheck[boxIndex][num] = true;
            }
        }
        return true;
    }

    static int solveSudoku(int[][] mat) {
        // Check validity before solving
        if (!isValidSudoku(mat))
            return -1;

        boolean solved = solveSudokuUtil(mat);
        if (!solved)
            return -1;
        return 1;
    }

    static void printSudoku(int[][] mat) {
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                System.out.print(mat[i][j] + " ");
            }
            System.out.println();
        }
    }

}
```

