class Result{
  /*     
   * Complete the 'inspectStrings' function below.
   * @params
   *   words -> A string array, which contains the strings
   *  
   * @return
   *   A String, which occurs the maximum numbers of times
   */
  static String inspectStrings(String[] words) {
    // Write your code here
      String res = words[0];
      int count = 0;
      Map<String, Integer> map = new HashMap<>();
      for(String s : words){
          map.put(s, map.getOrDefault(s,0)+1);
          if(map.get(s) > count){
              count = map.get(s);
              res = s;
          }
      }
      for(String s : words){
          int c = map.get(s);
          if(c == count){
              if(s.compareTo(res) > 0){
                  res = s;
              }
          }
      }
      return res;
  }
}