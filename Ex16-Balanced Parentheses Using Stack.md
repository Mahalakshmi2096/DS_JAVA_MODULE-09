# Ex16 Check for Balanced Parentheses Using Stack
## DATE: 04.10.2025
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Start the program.
2. Read an input string containing parentheses/brackets.
3. Create a stack to store opening brackets.
4. Traverse each character of the string:

     i) If the character is an opening bracket (, {, [, push it onto the stack.
   
     ii) If it is a closing bracket ), }, ]
   
           i) Check if the stack is empty: If yes, the string is unbalanced.
   
           ii) Otherwise, pop the top element from the stack and verify if it matches the current closing bracket.
   
           iii) If the brackets do not match, the string is unbalanced.
5. After traversal:
6. If the stack is empty, the string is balanced; otherwise, it's unbalanced.
7. Display the result.
8. End the program.  

## Program:
```
import java.util.Scanner;
class ArrayStack {
    private char[] stack;
    private int top;
    public ArrayStack(int capacity) {
        stack = new char[capacity];
        top = -1;
    }
    public void push(char ch) {
        stack[++top] = ch;
    }
    public char pop() {
        return stack[top--];
    }
    public boolean isEmpty() {
        return (top == -1);
    }
}
public class ParenChecker {
    // Checks if expr has balanced brackets
    public static boolean isBalanced(String expr) {
        ArrayStack st = new ArrayStack(expr.length());
        for (char ch : expr.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                st.push(ch);
            }
            else if (ch == ')' || ch == '}' || ch == ']') {
                if (st.isEmpty()) return false;
                char top = st.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return st.isEmpty();
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String expr = sc.nextLine();
        boolean ok = isBalanced(expr);
        System.out.println(ok);
        sc.close();
    }
}
```
Developed by: Mahalakshmi B

Reg No: 212224040182
## Output:
<img width="445" height="196" alt="image" src="https://github.com/user-attachments/assets/a30a387b-7d3b-4c98-b1ad-d8897fe61a4e" />

## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
