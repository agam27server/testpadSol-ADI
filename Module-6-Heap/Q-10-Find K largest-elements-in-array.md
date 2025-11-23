# Find K largest elements in array

```java
static void print(PriorityQueue<Integer> heap){
    int temp = heap.poll();
    System.out.print(temp);
}
static void printKLargest(int array[], int n, int k){
    PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());
    for(int i=0;i<array.length;i++){
        pq.add(array[i]);
    }
    for(int i=0;i<k-1;i++){
    print(pq);
    System.out.print(" ");
    }
    print(pq);
}
```