# Ex.No:1(A) INTRODUCTION TO JAVA PROGRAMMING, DATA TYPES, VARIABLES AND OPERATORS

## QUESTION:
Lovely has just started learning Java and is very excited about how to display messages on the screen. Her first mission is to understand how different types of print statements work:

System.out.print() → prints on the same line

System.out.println() → prints and moves to the next line

System.out.printf() → prints formatted output


## AIM:
To write a Java program that demonstrates the use of variables, data types, operators, and different print statements (print, println, and printf).

## ALGORITHM :
1.	Start the program.
2.	Import the required package java.util.* (optional).
3.	Declare variables of different data types (int, float, char, String).
4.	Perform simple arithmetic operations using operators.
5.	Use System.out.print() to display output on the same line.
6.	Use System.out.println() to display output on the next line.
7.	Use System.out.printf() to print formatted output.
8.	End the program.

## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## Sourcecode.java:
```java
import java.util.*;
public class Main
{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        String name=sc.next();
        int age=sc.nextInt();
        double num=sc.nextDouble();
        System.out.println("Hello, "+name);
        System.out.println("You are "+age+" years old");
        System.out.printf("Your favorite number is %.2f ",num);
    }
}
```


## OUTPUT:
<img width="766" height="385" alt="Screenshot 2025-11-14 105812" src="https://github.com/user-attachments/assets/8ca3a2e4-e913-4c3f-a8bf-73827075ab57" />


## RESULT:
Thus, the Java program demonstrating variables, data types, operators, and print statements was successfully executed.


# Ex.No:1(B) CONDITIONAL STATEMENT

## QUESTION:
In a haunted house, lights turn on or off based on the hour of entry:

If the hour is even and between 2 and 6 (inclusive), lights flicker.

If the hour is odd and between 7 and 11, lights stay off.

If the hour is 12, lights turn red.

Otherwise, the house is dark.


## AIM:
To write a Java program that uses conditional statements to determine the state of lights in a haunted house based on the hour of entry.

## ALGORITHM :
1. Start the program.

2. Import the necessary package java.util.*.

3. Create a Scanner object to read the hour input from the user.

4. Read the hour as an integer.

5. Check if the hour is even and between 2 and 6 (inclusive):

6. Display “Lights flicker”.

7. Else if the hour is odd and between 7 and 11:

8. Display “Lights stay off”.

9. Else if the hour is 12:

10. Display “Lights turn red”.
 
11. Display “The house is dark”.

12. End the program.

## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## Sourcecode.java:
```java
import java.util.*;
public class Demo
{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int a=sc.nextInt();
       if (a >= 2 && a <= 6 && a % 2 == 0) {
            System.out.println("Lights flicker");
        } else if (a>= 7 && a <= 11 && a % 2 != 0) {
            System.out.println("Lights off");
        } else if (a == 12) {
            System.out.println("Lights red");
        } else {
            System.out.println("Dark house");
        }
    }
}
```

## OUTPUT:
<img width="486" height="294" alt="Screenshot 2025-11-14 101547" src="https://github.com/user-attachments/assets/a64529b4-061c-436d-8ea4-55157b6e41b9" />





## RESULT:
Thus, the Java program to implement conditional statements for the haunted house lighting system was successfully executed.



# Ex.No:1(C) LOOPING STATEMENT

## QUESTION:
Construct a right-angled triangle star pattern using for loop.
## AIM:
To write a Java program using looping statements to print a right-angled triangle star pattern based on user input.

## ALGORITHM :
1.	Start the program.

2.	Import the necessary package 'java.util'

3. Read the number of rows from the user.

4. Use an outer loop to iterate through each row.

5. Use an inner loop to print stars (*) for each row.

6. Move to the next line after printing stars for each row.

7. End the program.


## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:

```java
import java.util.*;
public class TrianglePattern
{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        for (int i = 1; i <= n; i++) 
        {         
            for (int j = 1; j <= i; j++) 
            {      
                System.out.print("* ");
            }
            System.out.println();              
        }
    }
}
```




## OUTPUT:
<img width="399" height="395" alt="image" src="https://github.com/user-attachments/assets/07286d0c-5174-4702-8d58-34b630bd23d6" />



## RESULT:
Thus, the Java program using looping statements to print a right-angled triangle star pattern was successfully written, executed, and verified.


# Ex.No:1(D) ARRAYS

## QUESTION:
Write a Java program to find the index of a given element in an array

## AIM:
To write a Java program that reads an array of integers and finds the index of a given element within the array.

## ALGORITHM :
1.Start the program and read the size of the array n.

2.Read n integer elements and store them in the array a[ ].

3.Read the element x whose index needs to be found.

4.Traverse the array from index 0 to n-1:

     If a[i] == x, print the index i and terminate the program.

5.If the loop finishes without a match, print "Element not found".

6.End the program.	





## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int a[] = new int[n];
        for (int i = 0; i < n; i++) 
        {
        a[i] = sc.nextInt();
        }
        
        int x = sc.nextInt();
        for (int i = 0; i < n; i++) {
            if (a[i] == x) {
                System.out.println(i);
                return;
            }
            
        }
        System.out.println("Element not found");
        
    }
}
```




## OUTPUT:
<img width="558" height="590" alt="image" src="https://github.com/user-attachments/assets/0d53717f-affe-4aaf-b448-35ef728bee48" />



## RESULT:
Therefore the program successfully searches the array for the given element.


# Ex.No:1(E) STRINGS AND MATH FUNCTION

## QUESTION:
Write a Java program to find the absolute value of a number using Math.abs().

## AIM:
To write a Java program that finds the absolute value of a given number using the Math.abs() method.

## ALGORITHM :
1.Start the program and create a Scanner object.

2.Read a number n (can be integer or decimal) from the user.

3.Use the built-in function Math.abs(n) to compute its absolute value.

4.Display the calculated absolute value.

5.End the program.



## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```


## SOURCE CODE:
```java
import java.util.*;
public class demo
{
    public static void main(String[] args)
    {
        Scanner sc=new Scanner(System.in);
        double n=sc.nextDouble();
        System.out.println("Absolute value = "+Math.abs(n));
    }
}
```


## OUTPUT:
<img width="744" height="288" alt="image" src="https://github.com/user-attachments/assets/5fab9f43-7f0e-491d-bbad-5c3b7979703e" />



## RESULT:
Therefore the program successfully reads a number and calculates its absolute value.























