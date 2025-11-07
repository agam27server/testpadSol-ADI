class Result {
  static void countFrequency(String str) {
    // Write your code here
      int[] freq = new int[26];
      for(char i : str.toCharArray()){
          freq[i - 'a']++;
      }
      for(char i : str.toCharArray()){
          if(freq[i - 'a'] != 0){
              System.out.print(i+""+freq[i - 'a']+" ");
              freq[i - 'a'] = 0;
          }
      }
  }
}