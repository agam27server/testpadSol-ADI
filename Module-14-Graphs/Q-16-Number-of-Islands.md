# Number of Islands
```java
class Result {
  static int countIslands(int grid[][], int m, int n){
        int count =0;
        for(int i=0;i<m;i++){
            for(int j=0;j<n;j++){
                if(grid[i][j]==1){
                    count++;
                    dfs(i,j,m,n,grid);
                }
            }
        }
        return count;
    }
        //unmarks position
        public static  void dfs(int i,int j,int m,int n,int[][] grid){
            if(j<0 || j>=n || i<0 || i>=m || grid[i][j]==0)return;
             grid[i][j] = 0;
            dfs(i+1,j,m,n,grid);
            dfs(i-1,j,m,n,grid);
            dfs(i,j+1,m,n,grid);
            dfs(i,j-1,m,n,grid);
        }
}
```