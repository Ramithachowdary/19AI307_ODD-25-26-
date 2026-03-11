# Ex.No:3(E) INNER CLASS 
### ENUM

## QUESTION:
Write a Java program to define an enum named GameLevel with three constants: EASY, MEDIUM, and HARD.

## AIM:
To write a Java program that defines an enum named GameLevel with constants EASY, MEDIUM, and HARD, and allows the user to select a game level.

## ALGORITHM :
1. Define an enum GameLevel with constants: EASY, MEDIUM, HARD.

2. Read user input as a string and convert it to uppercase.

3. Use GameLevel.valueOf() to match the input with an enum constant.

4. If the value matches, print the selected game level.

5. If no match is found, catch IllegalArgumentException and show an error message.

6. Close the scanner in the finally block.




## PROGRAM:
 ```
/*
Program to implement a conditional statement using Java
Developed by: Ramitha chowdary S 
Register Number: 212224240130
*/
```


## SOURCE CODE:
```java
import java.util.Scanner;

enum GameLevel {
    EASY, MEDIUM, HARD;
}

public class Game {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String userInput = scanner.nextLine().toUpperCase();

        try {
            GameLevel level = GameLevel.valueOf(userInput);
            System.out.println("You selected game level: " + level);
        } catch (IllegalArgumentException e) {
            System.out.println("Invalid game level entered.");
        } finally {
            scanner.close();
        }
    }
}

```




## OUTPUT:
<img width="805" height="188" alt="514369907-fe75fd02-00e4-4672-8233-93e35f565e9f" src="https://github.com/user-attachments/assets/d54c3ab4-1f3f-4824-9f96-938190b73b16" />



## RESULT:
The program has been executed successfully and the desired output has been obtained.




