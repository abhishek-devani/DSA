# Solution

```java
class ListNode {
    public int key;
    public int val;
    public ListNode next;
    public ListNode prev;
    
    public ListNode(int key, int val) {
        this.val = val;
        this.key = key; 
        this.next = null;
        this.prev = null;
    }
}

public class Solution {

    HashMap<Integer, ListNode> hm = new HashMap<>();
    private int capacity;
    private int currentCapacity = 0;
    ListNode head = new ListNode(-1, -1);
    ListNode tail = new ListNode(-1, -1);
    
    public Solution(int capacity) {
        
        this.capacity = capacity;
        head.next = tail;
        tail.prev = head;

    }
    
    public int get(int key) {
        
        if (!hm.containsKey(key)) {
            return -1;
        }

        ListNode node = hm.get(key);
        int value = node.val;
        deleteNode(node);
        set(key, value);
        return value;

    }
    
    public void set(int key, int value) {
        
        ListNode node = new ListNode(key, value);
        if(hm.containsKey(key)){
            deleteNode(hm.get(key));
            insertNode(node);
        } else {
            if(currentCapacity < capacity){
                insertNode(node);
            }
            else{
                deleteNode(head.next);
                insertNode(node);
            }
        }

    }

    private void insertNode(ListNode node){

        ListNode lastNode = tail.prev;
        node.next = tail;
        tail.prev = node;
        node.prev = lastNode;
        lastNode.next = node;
        hm.put(node.key , node);
        currentCapacity++;
    }


    private void deleteNode(ListNode node){
        node.prev.next = node.next;
        node.next.prev = node.prev;  
        hm.remove(node.key);
        currentCapacity--;
    }

}
```

### Main Class

```java
public class Main {

    public static void main(String[] args) {
        // Create an instance of Solution with capacity 2
        Solution cache = new Solution(2);

        // Set key-value pairs in the cache
        cache.set(1, 1);
        cache.set(2, 2);

        // Retrieve and print values
        System.out.println("Value for key 1: " + cache.get(1)); // Output: 1
        System.out.println("Value for key 2: " + cache.get(2)); // Output: 2

        // Set a new key-value pair, which will evict the least recently used item (key 1)
        cache.set(3, 3);

        // Try to get the evicted key, it should return -1
        System.out.println("Value for key 1 after eviction: " + cache.get(1)); // Output: -1

        // Retrieve and print values for the remaining keys
        System.out.println("Value for key 2: " + cache.get(2)); // Output: 2
        System.out.println("Value for key 3: " + cache.get(3)); // Output: 3
    }
}
```

### Time Complexity
- O(1)

### Space Complexity
- O(1)