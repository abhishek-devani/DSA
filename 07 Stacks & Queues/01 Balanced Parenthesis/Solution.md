# Solution

```java
public class Solution {
    public int solve(String A) {

        Stack<Character> stk = new Stack<>();

        int n = A.length();

        for (int i = 0; i < n; i++) {
            char ch = A.charAt(i);
            if (stk.size() == 0) {
                stk.push(ch);
            } else if (ch == '{' || ch == '(' || ch == '[') {
                stk.push(ch);
            } else if (ch == ')') {
                char tmp = stk.pop();
                if (tmp != '(') {
                    return 0;
                }
            }  else if (ch == ']') {
                char tmp = stk.pop();
                if (tmp != '[') {
                    return 0;
                }
            }  else if (ch == '}') {
                char tmp = stk.pop();
                if (tmp != '{') {
                    return 0;
                }
            }
        }

        if (stk.size() == 0) {
            return 1;
        }
        return 0;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(n)