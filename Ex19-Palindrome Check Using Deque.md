# Ex19 Palindrome Check Using Deque
## DATE: 06.10.2025
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm
1. Start the program.
2. Read an input string from the user.
3. Remove all non-alphanumeric characters from the string.
4. Convert all characters to lowercase for uniform comparison.
5. Create a deque (double-ended queue).
6. Insert each character of the cleaned string into the deque.
7. While the deque has more than one element:
8. Remove one character from the front and one from the rear.
9. Compare both characters.
10. If they are not equal, the string is not a palindrome.
11. If all pairs match, the string is a palindrome.
12. Display the result.   

## Program:
```
import java.util.*;
public class PalindromeChecker {
    public static boolean isPalindrome(String message) {
        // Convert to lowercase and remove non-alphanumeric characters
        message = message.toLowerCase().replaceAll("[^a-z0-9]", "");        
        Deque<Character> deque = new ArrayDeque<>();
        // Add all characters to the deque
        for (char c : message.toCharArray()) {
            deque.addLast(c);
        }
        // Compare characters from both ends
        while (deque.size() > 1) {
            if (deque.pollFirst() != deque.pollLast()) {
                return false;  // Mismatch found
            }
        }
        return true;  // All characters matched
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        //System.out.println("Enter a message:");
        String input = scanner.nextLine();
        if (isPalindrome(input)) {
            System.out.println("Palindrome");
        } else {
            System.out.println("Not a palindrome");
        }
        scanner.close();
    }
}
```
Developed By: Mahalakshmi B

Reg No: 212224040182
## Output:
<img width="478" height="207" alt="image" src="https://github.com/user-attachments/assets/7a5c57d7-dd96-451a-9692-55863eb51d46" />

## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
