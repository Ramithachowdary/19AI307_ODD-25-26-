# Ex.No:2(A) CLASS AND OBJECT

## QUESTION:
Define a class Car with brand (String), color (String), and year (int). Create 2 different objects of Car  Assign values to attributes. Print the details of both cars.import java.util.Scanner;
## AIM:
To define a class Car with attributes brand, color, and year; create two objects of the class; assign values to their attributes; and print the details of both cars.

## ALGORITHM :
1. Define a class Car with three data members:

     String brand
     String color
     int year
 and a method printDetails() to display these values.

2. In the main() method, create a Scanner object to read user inputs.

3. Create the first object car1 and read its brand, color, and year from the user.

4. Create the second object car2 and read its brand, color, and year.

5. Call printDetails() for car1 to display its information.

6. Call printDetails() for car2 to display its information.

7.Close the scanner and end the program.


## PROGRAM:
 ```
/*
Program to implement a Class and Objects using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

class Car {
    String brand;
    String color;
    int year;

    void printDetails() {
        System.out.println("Brand: " + brand);
        System.out.println("Color: " + color);
        System.out.println("Year: " + year);
    }
}

class prog {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        
        Car car1 = new Car();
        car1.brand = scanner.nextLine();
        car1.color = scanner.nextLine();
        car1.year = scanner.nextInt();
        scanner.nextLine();

        
        Car car2 = new Car();
        car2.brand = scanner.nextLine();
        car2.color = scanner.nextLine();
        car2.year = scanner.nextInt();

        car1.printDetails();
        car2.printDetails();

        scanner.close();
    }
}
```


## OUTPUT:
<img width="597" height="685" alt="image" src="https://github.com/user-attachments/assets/05ebe553-f279-4f17-b125-675b4afd47bd" />


## RESULT:
Therefore,the program successfully creates two Car objects and assigns values to their attributes.


# Ex.No:2(B) METHODS

## QUESTION:
Write a method int cube(int x) that calls a method int square(int x) internally to calculate the cube as x * square(x).

## AIM:
To write a Java program that defines a method cube(int x) which internally calls the method square(int x) to compute the cube of a number.

## ALGORITHM :
1. Define a class demo with two methods:

     square(int n) → returns n * n.
     cube(int n) → returns n * square(n) by calling the square() method internally.

2. In the main class, read an integer input from the user.

3. Create an object of the demo class.

4. Call the cube() method using the object and print the result.

5. End the program.





## PROGRAM:
 ```
/*
Program to implement a Methods using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.util.*;
class demo
{
    public int square(int n)
    {
        return n*n;
    }
    public int cube(int n)
    {
        return n*square(n);
    }
    
}
public class main
{
    public static void main(String[] args)
    {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        demo d=new demo();
        System.out.println(d.cube(n));
    }
}
```


## OUTPUT:
<img width="392" height="243" alt="image" src="https://github.com/user-attachments/assets/aa929a40-c871-4a15-8d09-12604778a14b" />



## RESULT:
Therefore the program successfully computes the cube of a number by internally using the square method.



# Ex.No:2(C) ACCESS SPECIFIERS

## QUESTION:
Write a Java program to create a class called BankAccount with private instance variables accountNumber and balance. Provide public getter and setter methods to access and modify these variables.

## AIM:
To write a Java program that defines a class BankAccount with private attributes accountNumber and balance, and provides public getter and setter methods to access and modify these values.

## ALGORITHM :
1. Define a class BankAccount with two private instance variables:

        String accountNumber

        double balance

3. Create public getter and setter methods for both variables:

      getAccountNumber() and setAccountNumber()
   
   
      getBalance() and setBalance()

5. In the main() method, create a Scanner object to read input from the user.

6. Create an object of the BankAccount class.

7. Read the account number and balance from the user and store them using setter methods.

8. Retrieve and print the stored values using getter methods.

9. Close the Scanner and end the program.





## PROGRAM:
 ```
/*
Program to implement a Access Specifiers using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

class BankAccount {
   
    private String accountNumber;
    private double balance;

    
    public String getAccountNumber() {
        return accountNumber;
    }
    public void setAccountNumber(String accountNumber) {
        this.accountNumber = accountNumber;
    }

   
    public double getBalance() {
        return balance;
    }
    public void setBalance(double balance) {
        this.balance = balance;
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        BankAccount account = new BankAccount();

        String accNo = sc.nextLine();
        double bal = sc.nextDouble();

        account.setAccountNumber(accNo);
        account.setBalance(bal);

        System.out.println("Account Number: " + account.getAccountNumber());
        System.out.println("Balance: " + account.getBalance());

        sc.close();
    }
}
```

## OUTPUT:
<img width="826" height="465" alt="image" src="https://github.com/user-attachments/assets/972c4fcf-d9d0-43f8-bc30-518764a4d55e" />



## RESULT:
Therfore the program successfully stores account details using setter methods and retrieves them using getter methods.


# Ex.No:2(D) VARIABLE SCOPE AND CONSTRUCTOR

## QUESTION:
Write a class that uses a constructor to initialize variables and overrides toString() method.

## AIM:
To write a Java program that initializes object variables using a constructor and overrides the toString() method to display object details in a readable format.

## ALGORITHM :

1. Define a class Student with two instance variables:

     String name

     int age

2. Create a parameterized constructor to initialize these variables.

3. Override the toString() method to return the student details in a formatted string.

4. In the main() method:

    - Read the name and age from the user.

    - Create a Student object using the constructor.

5. Print the object, which automatically calls the overridden toString() method.

6. End the program.



## PROGRAM:
 ```
/*
Program to implement a Variable scope and Constructor using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:

```java
import java.util.Scanner;

class Student {
    String name;
    int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Student{name='" + name + "', age=" + age + "}";
    }
}

public class StudentDemo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String name = scanner.nextLine();
        int age = scanner.nextInt();

        Student student = new Student(name, age);
        System.out.println(student.toString());
    }
}
```




## OUTPUT:
<img width="896" height="395" alt="image" src="https://github.com/user-attachments/assets/0b280b01-a09a-4749-b733-41411f01b00a" />




## RESULT:
Therefore the program successfully creates a student object using the constructor.





# Ex.No:2(E) ACCESS MODIFIERS

## QUESTION:
Create a class Employee with method display(). Inside display(), return the current object using this. Create another method that calls display().printName()


## AIM:
To create an Employee class where the display() method returns the current object using this, and demonstrate calling display().printName() from another method.

## ALGORITHM :
1. Create a class Employee with a variable name.

2. Write a method setName() to assign value to name.

3. Write a method display() that returns the current object using return this;.

4. Write a method printName() to print the employee name.

5. Add another method show() that internally calls display().printName().

6. In the main() method, read the employee name from the user.

7.Create an Employee object and set the name.

8. Call both display().printName() and show() to demonstrate method chaining.





## PROGRAM:
 ```
/*
Program to implement a Access Modifiers using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

class Employee {
    String name;

    void setName(String name) {
        this.name = name;  
    }

    Employee display() {
        return this;  
    }

    void printName() {
        System.out.println("Employee Name: " + name);
    }
}

class prog {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String inputName = scanner.nextLine();

        Employee emp = new Employee();
        emp.setName(inputName);
        emp.display().printName();  
    }
}
```


## OUTPUT:

<img width="686" height="326" alt="image" src="https://github.com/user-attachments/assets/954fafa4-a638-4044-b666-3322017194cd" />


## RESULT:
Therefore the program successfully returns the current object using this inside the display() method.















