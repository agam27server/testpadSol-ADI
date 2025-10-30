# Print All Strings of N Bits

```java
class Solve
{
    // Recursive function to generate all binary strings
    void generateAllStrings(int n, int i, char currStr[], ArrayList<String> strs)
    { 
        // Base case: when all bits are filled
        if (i == n) {
            strs.add(new String(currStr)); // store string in ArrayList
            return;
        }
        // Place '0' at current position and recurse
        currStr[i] = '0';
        generateAllStrings(n, i + 1, currStr, strs);
        // Place '1' at current position and recurse
        currStr[i] = '1';
        generateAllStrings(n, i + 1, currStr, strs);
    } 
}
```

