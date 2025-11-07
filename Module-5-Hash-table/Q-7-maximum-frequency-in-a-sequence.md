import java.util.*;
class Result {
    static int maxFrequency(int A[], int n) {
        Map<Integer, Integer> map = new HashMap<>();
        int maxi = 0;        // maximum frequency
        int maxiEle = A[0];  // element with maximum frequency (smallest in case of tie)
        for (int i : A) {
            int freq = map.getOrDefault(i, 0) + 1;
            map.put(i, freq);
            if (freq > maxi) {
                maxi = freq;
                maxiEle = i;
            } else if (freq == maxi) {
                if (i < maxiEle) {  // tie-breaker: choose smaller element
                    maxiEle = i;
                }
            }
        }
        return maxiEle;
    }
}