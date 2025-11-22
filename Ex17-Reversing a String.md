# Ex17 Reversing a String Using Stack Data Structure
## DATE:04.10.2025
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm:
1. Start the program.
2. Read the input string from the user.
3. Create an empty stack of characters.
4. Traverse the string and push each character onto the stack.
5. Pop each character from the stack and append it to a new string — this gives the reversed string.
6. Display the reversed string.
7. Stop the program.

## Program:
```
import java.util.Scanner;
import java.util.Stack;

public class ReverseStringWithStack {

    public static String reverseString(String input) {
         Stack<Character> stack=new Stack<>();
        for(char ch:input.toCharArray())
        {
            stack.push(ch);
        }
        StringBuilder rev=new StringBuilder();
        while(!stack.isEmpty())
        {
            rev.append(stack.pop());
        }
        return rev.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        String reversed = reverseString(input);
        System.out.println(reversed);

        scanner.close();
    }
}
```
Developed By: Mahalakshmi B

Reg No: 212224040182
## Output:
<img width="546" height="206" alt="image" src="https://github.com/user-attachments/assets/a6f3d6f6-66f4-4e8e-820f-bbf89bc4c19b" />

## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
