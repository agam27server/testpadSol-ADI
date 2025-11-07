class Result {
  static int arraysEqualorNot(int[] A, int[] B) {
    // Write your code here
        Arrays.sort(A);
        Arrays.sort(B);
      for(int i = 0; i < A.length; i++){
          if(A[i]!=B[i]){
              return 0;
          }
      }
      return 1;
  }
}