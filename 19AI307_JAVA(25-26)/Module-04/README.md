# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:
If an Integer object is set to null, and you attempt to call .toString() on it, what happens? How can you prevent your code from throwing an exception in such cases?

## AIM:
To write a Java program that demonstrates how a NullPointerException occurs when accessing methods on a null Integer object, and how to handle it using a try–catch block.

## ALGORITHM :
1. Start the program.
2. Create a Scanner object to read an integer input from the user.
3. Read an integer value input.
4. If the input is 0, assign null to the Integer object num; otherwise assign the input value.
5. Use a try block to call num.toString():
   - If num is not null, print its string representation.
   - If num is null, a NullPointerException will be thrown.
6. Catch the NullPointerException and print "Null Integer".
7. Close the scanner.
8. End the program.

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

public class NullPointerIntegerExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int input = sc.nextInt();
        Integer num = (input == 0) ? null : input;

        try {
            System.out.println(num.toString());
        } catch (NullPointerException e) {
            System.out.println("Null Integer");
        }

        sc.close();
    }
}
```

## OUTPUT:
<img width="577" height="285" alt="image" src="https://github.com/user-attachments/assets/e1148027-987e-4477-a256-da7386dad2c1" />

## RESULT:
The program successfully demonstrates how invoking a method on a null `Integer` object triggers a `NullPointerException`, and shows how the exception can be caught and handled gracefully by printing `"Null Integer"`.




# Ex.No:4(B)  IMPLEMENT SOLID PRINCIPLES IN JAVA PROGRAM 

## QUESTION:
In a gaming lounge, there is only one master console power switch that controls all gaming consoles. Whenever a player turns on any console, it internally triggers the master power. The master switch must ensure only one instance is ever created, regardless of how many times it's accessed, to prevent power fluctuations.

Every time a player accesses the master switch, it logs an access count. Since the switch is Singleton, the count should increment globally and reflect shared state.

Input Format:

n
[Player1]
[Player2]
...
First line: Integer n – number of players turning on consoles

Next n lines: Each line contains the player's name.

 

Output Format:
For each player, print:

[PlayerName] accessed Master Power Switch. Total accesses so far: [count]


<img width="699" height="290" alt="image" src="https://github.com/user-attachments/assets/9b857649-79d5-4413-bfe6-09e4dd6ff5b2" />



## AIM:
To implement a Singleton master power switch that logs shared access counts whenever players turn on their consoles.


## ALGORITHM :
1. Start the program.

2. Create a Scanner object to take input from the user.

3. Read an integer n representing the number of players.

4. For each of the n players:
a. Read the player’s name.
b. Access the singleton instance of MasterPowerSwitch using getInstance().
c. Call logAccess() on the instance to increment and retrieve the total access count.
d. Print the message: [PlayerName] accessed Master Power Switch. Total accesses so far: [count].

5. End the program.




## PROGRAM:
 ```
/*
Program to implement a SOLID Principles in Java Program
Developed by: Ramitha chowdary S 
Register Number: 212224240130
*/
```

## SOURCE CODE:

```
import java.util.*;

class MasterPowerSwitch {
    private static MasterPowerSwitch instance;
    private int accessCount = 0;

    private MasterPowerSwitch() {}

    public static MasterPowerSwitch getInstance() {
        if (instance == null) {
            instance = new MasterPowerSwitch();
        }
        return instance;
    }

    public int logAccess() {
        accessCount++;
        return accessCount;
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) {
            String player = sc.nextLine();
            MasterPowerSwitch power = MasterPowerSwitch.getInstance();
            int count = power.logAccess();
            System.out.println(player + " accessed Master Power Switch. Total accesses so far: " + count);
        }
    }
}
```





## OUTPUT:


<img width="1125" height="244" alt="image" src="https://github.com/user-attachments/assets/1493987f-a93b-456e-a0b4-ff1c9bff3c7b" />


## RESULT:
The program ensures a single shared instance, incrementing and displaying the total access count for each player.




# Ex.No:4(C)  COMPOSITION IN JAVA

## QUESTION:
Create animals from two regions: "Africa" and "Asia". Use Abstract Factory to create families of animals (Herbivore, Carnivore). Print the interaction result.



## AIM:
To write a Java program demonstrating Composition and Abstract Factory Pattern by creating animal families of different regions and displaying interactions between herbivores and carnivores.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create interfaces Herbivore and Carnivore.
4. Create concrete animal classes (e.g., Wildebeest, Lion, Deer, Tiger) implementing those interfaces.
5. Create an abstract factory class for producing families of animals.
6. Implement region-based factories (AfricaFactory, AsiaFactory).
7. In the main program, instantiate factories and show interactions.
8. Print the result.
9. Stop the program.

## PROGRAM:
 ```
/*
Program to implement a Composition Concepts in Java
Developed by: Ramitha chowdary S 
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

interface Herbivore {}
interface Carnivore {
    void eat(Herbivore h);
}

class Wildebeest implements Herbivore {}
class Lion implements Carnivore {
    public void eat(Herbivore h) {
        System.out.println("Lion eats Wildebeest");
    }
}

class Buffalo implements Herbivore {}
class Tiger implements Carnivore {
    public void eat(Herbivore h) {
        System.out.println("Tiger eats Buffalo");
    }
}

interface AnimalFactory {
    Herbivore createHerbivore();
    Carnivore createCarnivore();
}

class AfricaFactory implements AnimalFactory {
    public Herbivore createHerbivore() { return new Wildebeest(); }
    public Carnivore createCarnivore() { return new Lion(); }
}

class AsiaFactory implements AnimalFactory {
    public Herbivore createHerbivore() { return new Buffalo(); }
    public Carnivore createCarnivore() { return new Tiger(); }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String region = sc.nextLine().toLowerCase();
        AnimalFactory factory;

        if (region.equals("africa")) factory = new AfricaFactory();
        else if (region.equals("asia")) factory = new AsiaFactory();
        else {
            System.out.println("Invalid region");
            return;
        }

        Carnivore carn = factory.createCarnivore();
        Herbivore herb = factory.createHerbivore();
        carn.eat(herb);
    }
}
```





## OUTPUT:

![java43](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/8b4be1e27b6fb5da0aa68915801ab1e6c9c7174e/19AI307_JAVA(25-26)/Module-04/DAY-3/java43.png)

## RESULT:
Thus, the program using Composition and Abstract Factory Pattern was successfully implemented and executed to create animal interactions for African and Asian regions.



# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
You are asked to simulate a simple Shape Drawing Tool using the Factory Design Pattern in Java.

You will implement a Shape interface with concrete classes for different shapes (Circle, Square, Rectangle). Using a ShapeFactory, your program will take shape names from user input and draw them accordingly. If the shape is unknown, print an error message.



## AIM:
To write a Java program that implements the Factory Design Pattern to create and draw shapes dynamically based on user input.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Shape interface containing a draw() method.
4. Create concrete classes Circle, Square, and Rectangle implementing Shape.
5. Create a ShapeFactory class with a method getShape(String shapeType).
6. In the main() method, accept user input for shape type.
7. Call factory method to get the appropriate object.
8. Draw the shape or print error if unknown.
9. Stop the program.


## PROGRAM:
 ```
/*
Program to implement a Abstract Factory Pattern using Java
Developed by: Ramitha chowdary S 
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

class Square implements Shape {
    public void draw() {
        System.out.println("Drawing Square");
    }
}

class Rectangle implements Shape {
    public void draw() {
        System.out.println("Drawing Rectangle");
    }
}

class ShapeFactory {
    public Shape getShape(String shapeType) {
        if (shapeType == null) {
            return null;
        }
        switch (shapeType.toLowerCase()) {
            case "circle":
                return new Circle();
            case "square":
                return new Square();
            case "rectangle":
                return new Rectangle();
            default:
                return null;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        ShapeFactory factory = new ShapeFactory();
        
        while (true) {
            String input = sc.nextLine().trim();
            if (input.equalsIgnoreCase("exit")) {
                break;
            }
            
            Shape shape = factory.getShape(input);
            if (shape != null) {
                shape.draw();
            } else {
                System.out.println("Invalid shape: " + input);
            }
        }
        sc.close();
    }
}
```






## OUTPUT:

![java44](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/b628a27d8352a971924fad5b0adffc7f5f8644ba/19AI307_JAVA(25-26)/Module-04/DAY-4/java44.png)

## RESULT:
Thus, the Java program to simulate Shape Drawing using the Factory Design Pattern was successfully implemented and executed.




# Ex.No:4(E) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:
Create a program that sends different types of notifications: "email", "sms", and "push". Use the Factory Pattern to generate the appropriate notification sender and call its notifyUser() method.



## AIM:
To write a Java program that demonstrates a Behavioral Pattern using the Factory Method, allowing different notification types to send messages through a common interface.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an interface Notification with method notifyUser().
4. Implement concrete classes: EmailNotification, SMSNotification, and PushNotification.
5. Create a NotificationFactory that returns the appropriate object based on user input.
6. In main(), get the notification type from the user.
7. Call the notifyUser() method of the returned object.
8. If no valid type is provided, display an error.
9. Stop the program.





## PROGRAM:
 ```
/*
Program to implement a Behaviour Pattern using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

interface Notification {
    void notifyUser();
}

// ===== Concrete Notifications =====
class EmailNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Email Notification");
    }
}

class SMSNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending SMS Notification");
    }
}

class PushNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Push Notification");
    }
}

// ===== Factory =====
class NotificationFactory {
    public Notification createNotification(String type) {
        if (type == null) return null;
        switch (type.toLowerCase()) {
            case "email":
                return new EmailNotification();
            case "sms":
                return new SMSNotification();
            case "push":
                return new PushNotification();
            default:
                return null;
        }
    }
}

// ===== Main =====
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        NotificationFactory factory = new NotificationFactory();

        while (true) {
            String input = sc.nextLine().trim();
            if (input.equalsIgnoreCase("exit")) break;

            Notification n = factory.createNotification(input);
            if (n != null) {
                n.notifyUser();
            } else {
                System.out.println("Invalid notification type: " + input);
            }
        }

        sc.close();
    }
}
```






## OUTPUT:

![java45](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/c6316a5904f4a174dd995f6b7d7c47b65f677921/19AI307_JAVA(25-26)/Module-04/DAY-5/java45.png)

## RESULT:
Thus, the program demonstrating the Behavioral Pattern using Factory Method to generate different notification types was successfully implemented and executed.






