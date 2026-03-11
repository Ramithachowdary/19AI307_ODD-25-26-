# Ex.No:3(F) WRAPPER CLASS

## QUESTION:
Write a Java program to find the square root of a number using Double wrapper class.

## AIM:
To write a Java program that reads a number in string format, converts it into a double, and prints its square root using the `Math.sqrt()` function.

## ALGORITHM :
1. Start the program.
2. Create a `Scanner` object to read input from the user.
3. Read a string value representing a number.
4. Convert the string to a `Double` using `Double.parseDouble()`.
5. Use `Math.sqrt()` to compute the square root of the number.
6. Display the result in the required format.
7. End the program.

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
import java.util.*;

public class Main
{
    public static void main(String[] args)
    {
        Scanner s = new Scanner(System.in);
        String str = s.next();
        
        Double num = Double.parseDouble(str);
        System.out.println("Square root of "+num+" is: "+(Math.sqrt(num)));
    }
}
```

## OUTPUT:
<img width="741" height="233" alt="image" src="https://github.com/user-attachments/assets/e890e0d1-6301-45de-ba69-890c05df00ba" />

## RESULT:
The program successfully reads a numeric string, converts it to a double value, computes its square root, and displays the result.




