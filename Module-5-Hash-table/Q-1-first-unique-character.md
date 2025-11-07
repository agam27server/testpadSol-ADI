class Result {
  static int firstUniqueChar(String str) {
      int[] freq = new int[26];
      for(int i = 0; i < str.length(); i++){
          char ch = str.charAt(i);
          freq[ch - 'a']++;
      }
      for(int i = 0; i<str.length(); i++){
          char ch = str.charAt(i);
          if(freq[ch - 'a'] == 1){
              return i;
          }
      }
      return -1;
  }
}