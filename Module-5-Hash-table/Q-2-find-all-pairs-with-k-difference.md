class Result {
    static int getPairsCount(int arr[], int n, int k) {
        Set<Integer> set = new HashSet<>();
        int count = 0;
        // Add all elements to set
        for (int num : arr) {
            set.add(num);
        }
        // Check for each element if (num + k) exists
        for (int num : arr) {
            if (set.contains(num + k)) {
                count++;
            }
        }
        return count;
    }
}