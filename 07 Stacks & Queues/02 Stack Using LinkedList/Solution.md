# Solution

## StackUsingLinkedList Class

```java
public class StackUsingLinkedList {

    private static class Node {
        int val;
        Node next;

        Node (int val, Node next) {
            this.val = val;
            this.next = next;
        }
    }

    Node h = null;
    int c = 0;

    public void push(int x) {
        Node nn = new Node(x, null);
        nn.next = h;
        h = nn;
        c++;
    }

    public int pop() {
        if (h == null) {
            throw new EmptyStackException();
        }
        int val = h.val;
        h = h.next;
        c--;
        return val;
    }

    public int size() {
        return c;
    }

    public int top() {
        if (h == null) {
            throw new EmptyStackException();
        }
        return h.val;
    }

}
```

---
## Main Class

```java
public class Main {

    public static void main(String[] args) {

        // Creating an instance of the StackUsingLinkedList class
        StackUsingLinkedList stack = new StackUsingLinkedList();

        // Pushing elements onto the stack
        stack.push(5);
        stack.push(10);
        stack.push(15);

        // Displaying the size of the stack
        System.out.println("Size of the stack: " + stack.size()); // ans = 3

        // Displaying the top element of the stack
        try {
            System.out.println("Top element of the stack: " + stack.top()); // ans = 15
        } catch (EmptyStackException e) {
            System.out.println("Stack is empty");
        }

        // Popping elements from the stack
        try {
            System.out.println("Popped element: " + stack.pop()); // ans = 15
        } catch (EmptyStackException e) {
            System.out.println("Stack is empty");
        }

        try {
            System.out.println("Popped element: " + stack.pop()); // ans = 10
        } catch (EmptyStackException e) {
            System.out.println("Stack is empty");
        }

        try {
            System.out.println("Top element of the stack: " + stack.top()); // ans = 5
        } catch (EmptyStackException e) {
            System.out.println("Stack is empty");
        }

        // Displaying the size of the stack after popping
        System.out.println("Size of the stack after popping: " + stack.size()); // ans = 1

        // Pushing element
        stack.push(21);
        System.out.println("Size of the stack after pushing: " + stack.size()); // ans = 2
        System.out.println("Top element of the stack: " + stack.top()); // ans = 21

    }
}
```

### Time Complexity
- O(1)

### Space Complexity
- O(1)