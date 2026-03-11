# Ex.No:5(A) INPUTSTREAMREADER 

## QUESTION:
Write a Java program to write characters to a file using FileWriter.



## AIM:
To write a Java program that writes character data into a text file using the FileWriter class.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a FileWriter object and specify the filename.
4. Write characters to the file using the write() method.
5. Close the FileWriter to save the data.
6. End the program.




## PROGRAM:
 ```
/*
Program to implement a InputStreamReader using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.io.*;
import java.util.Scanner;

public class FileWriterExampleUserInput {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            String fileName = sc.nextLine();
            String content = sc.nextLine();
            FileWriter fw = new FileWriter(fileName);
            fw.write(content);
            fw.close();

            System.out.println("File written successfully.");
        } catch (IOException e) {
            System.out.println("Error writing to file: " + e.getMessage());
        } finally {
            sc.close();
        }
    }
}
```






## OUTPUT:

![java51](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/a9261fe7fb8a08b278b91f6a1a979055f59755dc/19AI307_JAVA(25-26)/Module-05/DAY-1/java51.png)

## RESULT:
Thus, the Java program to write characters to a file using FileWriter was successfully executed and verified.




