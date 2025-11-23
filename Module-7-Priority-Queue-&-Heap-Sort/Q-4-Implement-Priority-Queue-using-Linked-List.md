# Implement Priority Queue using Linked List

```java
/* class QueueNode
{
  int data;
  int priority;
  QueueNode next;
  public QueueNode(int data, int p) 
  {
    this.data = data;
    this.priority = p;
  }
} is provided to you. */

class PQueueLL
{
  public QueueNode front, rear;

  public void EnQueue(int data, int priority)
  {
    QueueNode newNode = new QueueNode(data, priority);

    if (front == null) {
      front = rear = newNode;
      return;
    }

    // Case 2: New node has highest priority (lowest number)
    if (priority < front.priority) {
      newNode.next = front;
      front = newNode;
      return;
    }

    QueueNode temp = front;

    while (temp.next != null && temp.next.priority <= priority) {
      temp = temp.next;
    }

    newNode.next = temp.next;
    temp.next = newNode;

      if (newNode.next == null) {
      rear = newNode;
    }
  }

  public int DeQueue()
  {
    if (front == null)
      return -1;  

    int result = front.data;
    front = front.next;

    if (front == null)
      rear = null;

    return result;
  }
}

```