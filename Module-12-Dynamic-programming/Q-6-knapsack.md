class Result
{
    static int solve(int val[], int weight[], int n, int capacity, int index, int[][] dp){
        if(index == 0){
            if(weight[index] <= capacity){
                return val[index];
            } else {
                return 0;
            }
        }
        // If already computed
        if(dp[index][capacity] != -1){
            return dp[index][capacity];
        }
        int include = 0;
        if(weight[index] <= capacity){
            include = val[index] + solve(val, weight, n, capacity - weight[index], index - 1, dp);
        }
        int exclude = solve(val, weight, n, capacity, index - 1, dp);
        // Save the result in dp table
        dp[index][capacity] = Math.max(include, exclude);
        return dp[index][capacity];
    }
    static int zeroOneKnapsack(int val[], int weight[], int n, int capacity){
        int[][] dp = new int[n][capacity + 1];
        for(int i = 0; i < n; i++){
            Arrays.fill(dp[i], -1);
        }
        return solve(val, weight, n, capacity, n - 1, dp);
    }
}