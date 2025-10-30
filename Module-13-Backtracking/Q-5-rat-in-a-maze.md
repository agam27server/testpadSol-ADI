# Rat in a Maze

```java
class Result {
  private static boolean isSafe(int x, int y, boolean[][] visited, int size) {
        return (x >= 0 && x < size && y >= 0 && y < size && !visited[x][y]);
  }
  public static int solve(int maze[][], int size, int i, int j, boolean[][] visited){
      if(maze[i][j] == -1){
          return 0;
      }
      if(i == size-1 && j == size-1){
          return 1;
      }
      visited[i][j] = true;
      int total = 0;
        if (isSafe(i, j + 1, visited, size)) total += solve(maze, size, i, j + 1, visited); // right
        if (isSafe(i + 1, j, visited, size)) total += solve(maze, size, i + 1, j, visited); // down
      visited[i][j] = false;
      return total;

  }
  public static int solveMaze(int maze[][], int size) {
    // Write your code here
    boolean[][] visited = new boolean[size][size];
    return  solve(maze,size,0,0,visited);
  }
}
```

