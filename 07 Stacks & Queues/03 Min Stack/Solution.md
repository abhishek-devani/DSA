# Solution

## MinStack Class

```java
public class MinStack {

    Stack<Integer> stack = new Stack<>();
    Stack<Integer> minStack = new Stack<>();

    public void push(int x) {
        stack.push(x);
        if (minStack.isEmpty()) {
            minStack.push(x);
        } else {
            minStack.push(Math.min(minStack.peek(), x));
        }
    }

    public int pop() {
        minStack.pop();
        return stack.pop();
    }

    public int size() {
        return stack.size();
    }

    public int top() {
        return stack.peek();
    }

    public int getMin() {
        return minStack.peek();
    }

}
```

---
## Main Class

```java
public class Main {

    public static void main(String[] args) {

        MinStack stack = new MinStack();

        stack.push(5);
        stack.push(10);
        stack.push(15);
        stack.push(1);
        stack.push(3);

        System.out.println("Minimum value from stack: " +stack.getMin()); // ans = 1
        stack.pop();
        System.out.println("Minimum value from stack: " +stack.getMin()); // ans = 1
        stack.pop();
        System.out.println("Minimum value from stack: " +stack.getMin()); // ans = 5
        stack.pop();
        System.out.println("Minimum value from stack: " +stack.getMin()); // ans = 5

    }
}
```

### Time Complexity
- O(1)

### Space Complexity
- O(1)