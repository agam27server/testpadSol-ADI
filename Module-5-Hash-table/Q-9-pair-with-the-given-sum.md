class Result {
    static boolean pairSum(int arr[], int n, int k) {
        Map<Integer, Boolean> map = new HashMap<>();
        for (int i = 0; i < n; i++) {
            int complement = k - arr[i];
            if (map.containsKey(complement)) {
                return true; // pair found
            }
            map.put(arr[i], true); // mark current element as seen
        }
        return false; // no pair found
    }}