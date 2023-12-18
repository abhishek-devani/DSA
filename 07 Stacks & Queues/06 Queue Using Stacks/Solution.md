# Solution

## QueueUsingStack Class

```java
public class QueueUsingStack {

    Stack<Integer> stack1 = new Stack<>();
    Stack<Integer> stack2 = new Stack<>();

    public void enQueue(int x) {
        stack1.push(x);
    }

    public int deQueue() {
        if (stack1.isEmpty() && stack2.isEmpty()) {
            return -1;
        }
        if (stack2.isEmpty()) {
            while (!stack1.isEmpty()) {
                stack2.push(stack1.pop());
            }
        }
        return stack2.pop();
    }

    public int peek() {
        if (stack1.isEmpty() && stack2.isEmpty()) {
            return -1;
        }
        if (stack2.isEmpty()) {
            while (!stack1.isEmpty()) {
                stack2.push(stack1.pop());
            }
        }
        return stack2.peek();
    }

    public boolean isEmpty() {
        if (stack1.isEmpty() && stack2.isEmpty()) {
            return true;
        }
        return false;
    }

}
```

---
## Main Class

```java
public class Main {
    public static void main(String[] args) {

        QueueUsingStack queue = new QueueUsingStack();

        queue.enQueue(20);
        System.out.println(queue.isEmpty());
        System.out.println(queue.peek());
        System.out.println(queue.deQueue());
        System.out.println(queue.isEmpty());
        queue.enQueue(30);
        System.out.println(queue.peek());
        queue.enQueue(40);
        System.out.println(queue.peek());

    }
}
```

### Time Complexity
- **Average TC:** O(1)

### Space Complexity
- O(n)