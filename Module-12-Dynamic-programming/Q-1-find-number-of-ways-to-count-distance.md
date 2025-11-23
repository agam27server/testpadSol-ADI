# Find Number of Ways to Count Distance

```java
class Result {
    static int solve(int d, int k) {
        // base case
        if (d == 0) {
            return 1;  // one valid way (no more steps needed)
        }
        if (d < 0) {
            return 0;  // invalid way
        }
        int ans = 0;
        // try all jumps from 1 to k
        for (int i = 1; i <= k; i++) {
            ans += solve(d - i, k);
        }
        return ans;
    }
    static int totalWaysToDistance(int d, int k) {
        return solve(d, k);
    }
}
```
