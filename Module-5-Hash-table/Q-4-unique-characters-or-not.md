class Result {
    // Function to print YES if all characters are unique, NO otherwise
    static boolean isUniqueChars(String str) {
        int n = str.length();
        for (int i = 0; i < n; i++) {
            char c1 = str.charAt(i);
            for (int j = i + 1; j < n; j++) {
                char c2 = str.charAt(j);
                if (c1 == c2) {
                    //System.out.println("NO");
                    return false; // stop as soon as duplicate is found
                }
            }
        }
        //System.out.println("YES"); // all characters are unique
        return true;
    }
}