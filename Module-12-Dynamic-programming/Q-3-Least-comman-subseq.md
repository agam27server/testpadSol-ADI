# Longest Common Subsequence

```java
import java.util.*;
class Result {
    static int solve(String s1, String s2, int i, int j, int[][] dp) {
        // Base case
        if (i == s1.length() || j == s2.length()) {
            return 0;
        }
        // If already computed, return cached value
        if (dp[i][j] != -1) {
            return dp[i][j];
        }
        // If characters match
        if (s1.charAt(i) == s2.charAt(j)) {
            dp[i][j] = 1 + solve(s1, s2, i + 1, j + 1, dp);
        } 
        // If not match - explore both possibilities
        else {
            dp[i][j] = Math.max(
                solve(s1, s2, i + 1, j, dp),
                solve(s1, s2, i, j + 1, dp)
            );
        }
        return dp[i][j];
    }
    static int longestCommonSubsequence(String str1, String str2) {
        int n = str1.length();
        int m = str2.length();
        int[][] dp = new int[n][m];
        // Initialize dp with -1
        for (int[] row : dp) {
            Arrays.fill(row, -1);
        }
        return solve(str1, str2, 0, 0, dp);
    }
}
```
