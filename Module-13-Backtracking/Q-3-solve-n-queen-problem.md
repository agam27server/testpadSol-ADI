```java
class Result 
{
// Complete this function to check placing queen at board[row][col] is safe or not by checking current row, left diagonal & right diagonal.
  int isSafe(int board[][], int row, int col, int N) 
  { 
    //row check
      int i = row;
      int j = col;
      
      while(j >= 0){
          if(board[i][j] == 1){
              return 0;
          }
          j--;
      }
      
      //upper dia
      i = row;
      j = col;
      
      while(j >= 0 && i >= 0){
          if(board[i][j] == 1){
              return 0;
          }
          j--;
          i--;
      }
      
      //lower dia
      i = row;
      j = col;
      
      while(j >=0  && i < N){
          if(board[i][j] == 1){
              return 0;
          }
          i++;
          j--;
      }
      
      return 1;
  }
  ArrayList<Integer> fillSol(int board[][], int N){
      //System.out.print(" entered ");
      ArrayList<Integer> temp = new ArrayList<>();
          for(int i = 0; i < N; i++){
              for(int  j = 0; j < N; j++){
                  if(board[i][j] == 1){
                      temp.add(j);
                  }
              }
          }
      return temp;
  }
   void solve(int board[][], int col,int N, ArrayList<ArrayList<Integer> > sol){
       //badse case
       if(col == N){
           ArrayList<Integer> temp = fillSol(board,N);
           sol.add(temp);
           return;
       }
       
       for(int i = 0; i < N; i++){
           if(isSafe(board, i, col, N) == 1){
               board[i][col] = 1;
               
               solve(board,col+1,N,sol);
               
               board[i][col] = 0;
           }
       }
   }
// Complete this function to solve the problem and save the answers in sol ArrayList as required.
  boolean solveNQUtil(int board[][], int col, int N, ArrayList<ArrayList<Integer> > sol)
  { 
      for(int i = 0; i < N; i++){
          for(int  j = 0; j < N; j++){
              board[i][j] = 0;
          }
      }
      solve(board,col,N,sol);
      
      return sol.size() > 0;
  } 
}
```