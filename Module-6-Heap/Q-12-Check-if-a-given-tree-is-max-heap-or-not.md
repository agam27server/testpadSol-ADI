# Check if a given tree is max-heap or not

```java
static boolean isTrue(int array[],int n,int i){
    int largest = i;
    int left = 2 * i + 1;
    int right = 2 * i + 2;
    if (left < n && array[left] > array[largest]) {
        largest = left;
    }
    if (right < n && array[right] > array[largest]) {
        largest = right;
    }
    if (largest != i) {
        return false; 
    }
    return true;
}
static int isMaxHeap(int array[], int n){
  for(int i = n/2-1 ; i>=0;i--){
     if(! isTrue(array,n,i)){
         return 0;
     }
  }
    return 1;
}
```