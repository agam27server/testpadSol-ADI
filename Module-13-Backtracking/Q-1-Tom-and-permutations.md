```java
class Solve {
  /*
   * Return all the permutations of the given string in any order,
   * as they will be sorted at the back-end before printing.
   */
    static void swap(ArrayList<Character> temp, int i, int j){
        char tempEle = temp.get(i); 
        temp.set(i, temp.get(j));   
        temp.set(j, tempEle);     
    }
    static void permuteStrings(int i, ArrayList<String> res, String str, ArrayList<Character> temp){
        if(i >= str.length()){
            //System.out.println(temp.toString());
            StringBuilder sb = new StringBuilder();
            for (char c : temp) sb.append(c);
            res.add(sb.toString());
            return;
        }
        for(int j = i; j < str.length(); j++){
            swap(temp,i,j);
            permuteStrings(i+1,res,str,temp);
            swap(temp,i,j);
        }
    } 
  ArrayList<String> permute(String str) {
    // Write your code here
      ArrayList<String> res = new ArrayList<>();
      ArrayList<Character> temp = new ArrayList<>();
      char[] charArray = str.toCharArray();
      for (char ch : charArray) {
            temp.add(ch);
        }
      permuteStrings(0,res,str,temp);
      return res;
  }
}
```