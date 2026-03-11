# Ex.No:3(A) INHERITANCE AND AGGREGATION

## QUESTION:
A jewelry store tracks gold rates for different types of customers. The base class is Customer with attributes like customerId, name, and purchaseWeight (in grams). There are two types of customers: RegularCustomer and PremiumCustomer. RegularCustomer gets a fixed discount of 2% on the gold rate per gram. PremiumCustomer gets a 5% discount plus a special cashback. The base gold rate per gram is input at runtime. For each customer, calculate the final price they pay:

       
       
      finalPrice = purchaseWeight * (goldRatePerGram - discount)


For PremiumCustomer, additionally show cashback amount (which is 1% of the final price).

## AIM:
To build an inheritance-based Java program that calculates the final price of gold for different types of customers (Regular and Premium), applying respective discounts and showing cashback for premium customers.

## ALGORITHM :
1. Create a base class Customer with attributes: customerId, name, purchaseWeight, and goldRatePerGram.

2. Create method getDiscountRate() in base class returning 0 (default).

3. Create method calculateFinalPrice() that:

        calculates discount per gram → discountAmount = goldRatePerGram * (discountRate/100)

        calculates effective rate → effectiveRate = goldRatePerGram - discountAmount

  returns → finalPrice = purchaseWeight * effectiveRate

4. Override display() in base class to show general customer details.

5. Create child class RegularCustomer:

       Override getDiscountRate() to return 2%.

       Override display() to show customer type as Regular.

6. Create child class PremiumCustomer:

       Override getDiscountRate() to return 5%.

7.  Add calculateCashback() → returns 1% of final price.

8.  Override display() to show final price + cashback.

9.  Call display() to show the complete bill with discounts.





## PROGRAM:
 ```
/*
Program to implement a Inheritance and Aggregation using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:
```
import java.util.Scanner;
import java.text.DecimalFormat;

class Customer {
    String customerId, name;
    double purchaseWeight, goldRatePerGram;

    Customer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        this.customerId = customerId;
        this.name = name;
        this.purchaseWeight = purchaseWeight;
        this.goldRatePerGram = goldRatePerGram;
    }

    double getDiscountRate() {
        return 0;
    }

    double calculateFinalPrice() {
        double discountAmount = goldRatePerGram * getDiscountRate() / 100;
        double effectiveRate = goldRatePerGram - discountAmount;
        return purchaseWeight * effectiveRate;
    }

    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: General");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
        
    }
}

class RegularCustomer extends Customer {

    RegularCustomer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        super(customerId, name, purchaseWeight, goldRatePerGram);
    }

    @Override
    double getDiscountRate() {
        return 2.0;
    }

    @Override
    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: Regular");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: 2%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
       
    }
}

class PremiumCustomer extends Customer {

    PremiumCustomer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        super(customerId, name, purchaseWeight, goldRatePerGram);
    }

    @Override
    double getDiscountRate() {
        return 5.0;
    }

    double calculateCashback() {
        return calculateFinalPrice() * 0.01;
    }

    @Override
    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: Premium");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: 5%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
        System.out.println("Cashback: " + df.format(calculateCashback()));
        
    }
}

public class GoldRateSystem {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Input 1
        String type1 = sc.next();
        Customer cust1;
        if (type1.equalsIgnoreCase("Regular")) {
            cust1 = new RegularCustomer(sc.next(), sc.next(), sc.nextDouble(), sc.nextDouble());
        } else {
            cust1 = new PremiumCustomer(sc.next(), sc.next(), sc.nextDouble(), sc.nextDouble());
        }

        
        cust1.display();
     

        sc.close();
    }
}
```




## OUTPUT:
<img width="884" height="700" alt="image" src="https://github.com/user-attachments/assets/bc4bc233-2418-404a-88cc-490c1d83bc24" />



## RESULT:
Therefore the program successfully applies different discount rules for regular and premium customers.






# Ex.No:3(b) POLYMORPHISM

## QUESTION:
Write a Java program to create a class Vehicle with a method called speedUp(). Create two subclasses Car and Bicycle. Override the speedUp() method in each subclass to increase the vehicle's speed differently.

## AIM:
To create a Java program demonstrating method overriding by defining a base class Vehicle with a speedUp() method and overriding it in subclasses Car and Bicycle to increase speed differently.

## ALGORITHM :
1. Create a parent class Vehicle with an integer variable speed and a method speedUp(int increment) that increases speed normally.

2. Create a subclass Car that overrides speedUp() to increase speed by double the increment.

3. Create a subclass Bicycle that overrides speedUp() to increase speed normally (same as parent but customized message).

4. Read vehicle type and increment value from user.

5. Based on the type, create an object of Car, Bicycle, or Vehicle.

6. Call the speedUp(increment) method to show polymorphic behavior.




## PROGRAM:
 ```
/*
Program to implement a Polymorphism using Java
Developed by: Ramitha chowdary S
Register Number: 212224240130
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

// Parent class
class Vehicle {
    int speed = 0;

    void speedUp(int increment) {
        speed += increment;
        System.out.println("Vehicle speed increased to: " + speed + " km/h");
    }
}


class Car extends Vehicle {
    @Override
    void speedUp(int increment) {
        speed += increment * 2;
        System.out.println("Car speed increased to: " + speed + " km/h");
    }
}


class Bicycle extends Vehicle {
    @Override
    void speedUp(int increment) {
        speed += increment;
        System.out.println("Bicycle speed increased to: " + speed + " km/h");
    }
}


public class TestVehicles {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String type = sc.nextLine().toLowerCase();
        int increment = sc.nextInt();

        Vehicle vehicle;
        if (type.equals("car")) {
            vehicle = new Car();
        } else if (type.equals("bicycle")) {
            vehicle = new Bicycle();
        } else {
            vehicle = new Vehicle();
        }

        vehicle.speedUp(increment);
    }
}
```






## OUTPUT:
<img width="921" height="437" alt="image" src="https://github.com/user-attachments/assets/5c317382-efe2-4ec9-a2cf-67b2d4db68b4" />



## RESULT:
Therefore the  program successfully demonstrates method overriding by applying different speed increase behaviors for car and bicycle.






# Ex.No:3(C) ABSTRACTION

## QUESTION:
Create abstract class GameScore with method finalScore().  
Subclasses:
ArcadeGame: score = baseScore + (level × 100)
PuzzleGame: score = (attempts ≤ 3) ? 1000 - (attempts × 100) : 500

## AIM:
To write a Java program that uses an abstract class to calculate final game scores for two types of games:  
ArcadeGame and PuzzleGame, each implementing its own scoring logic.

## ALGORITHM:
1. Create an abstract class `GameScore` with the abstract method `finalScore()`.
2. Create subclass `ArcadeGame` with:
   - Attributes: `base`, `level`
   - Scoring rule: `finalScore = base + (level × 100)`
3. Create subclass `PuzzleGame` with:
   - Attribute: `attempts`
   - Scoring rule:
     - If attempts ≤ 3 → `finalScore = 1000 - (attempts × 100)`
     - Else → `finalScore = 500`
4. In the `main` method:
   - Read `type` (1 for ArcadeGame, 2 for PuzzleGame)
   - If `type == 1`:
     - Read `base` and `level`
     - Create `ArcadeGame` object
   - Else:
     - Read `attempts`
     - Create `PuzzleGame` object
   - Call `finalScore()` and print the result.
5. End the program.

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

abstract class GameScore
{
    abstract int finalScore();
}

class ArcadeGame extends GameScore
{
    int base;
    int level;
    ArcadeGame(int base,int level)
    {
        this.base=base;
        this.level=level;
    }
    @Override
    int finalScore()
    {
        return (base+(level*100));
    }
}
class PuzzleGame extends GameScore
{
    int attempts;
    PuzzleGame(int attempts)
    {
        this.attempts=attempts;
    }
    @Override
    int finalScore()
    {
        return ((attempts <= 3) ? 1000 - (attempts * 100) : 500);
    }
}
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int type = sc.nextInt();
        GameScore game;
        
        if (type == 1) {
            int base = sc.nextInt();
            int level = sc.nextInt();
            game = new ArcadeGame(base, level);
        } else {
            int attempts = sc.nextInt();
            game = new PuzzleGame(attempts);
        }
        
        System.out.println(game.finalScore());
    }
}
```

## OUTPUT:
<img width="354" height="206" alt="image" src="https://github.com/user-attachments/assets/c7d29ada-3636-4732-847f-28a95ba50bc8" />

## RESULT:
The program successfully calculates and displays the final score based on game type and user input using abstract methods and dynamic method dispatch.






# Ex.No:3(D) INTERFACE 

## QUESTION:
Two types of traffic controllers decide whether a vehicle can pass based on signal color. The decision logic varies by controller.
AggressiveController: Allows only if "GREEN".
DefensiveController: Allows for "GREEN" or "YELLOW".

## AIM:
To develop a Java program that decides whether a vehicle can move or must stop based on the signal color and the type of traffic controller (Aggressive or Defensive) using interfaces.

## ALGORITHM :
1. Define an interface `TrafficController` with the method:
   - `boolean canGo(String signalColor)`
2. Create class `AggressiveController` implementing the interface:
   - Allows passage only if the signal color is GREEN.
3. Create class `DefensiveController` implementing the interface:
   - Allows passage if the signal color is GREEN or YELLOW.
4. In the `main` method:
   - Read `color` (signal color)
   - Read `type` (controller type: 1 or 2)
5. Based on `type`:
   - If 1 → create `AggressiveController`
   - Else → create `DefensiveController`
6. Call `canGo(color)` to check permission.
7. If true → print `"GO"`
   - Else → print `"STOP"`
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
```
import java.util.*;

interface TrafficController {
    boolean canGo(String signalColor);
}

class AggressiveController implements TrafficController {
    public boolean canGo(String signalColor) {
        return signalColor.equalsIgnoreCase("GREEN");
    }
}

class DefensiveController implements TrafficController {
    public boolean canGo(String signalColor) {
        return signalColor.equalsIgnoreCase("GREEN") || signalColor.equalsIgnoreCase("YELLOW");
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String color = sc.next();
        int type = sc.nextInt();

        TrafficController ctrl = (type == 1) ? new AggressiveController() : new DefensiveController();

        if (ctrl.canGo(color))
            System.out.println("GO");
        else
            System.out.println("STOP");
    }
}
```

## OUTPUT:
<img width="431" height="202" alt="image" src="https://github.com/user-attachments/assets/893c86c5-b2f8-4240-8d2b-98ca05b093a6" />

## RESULT:
The program successfully determines whether a vehicle can move based on the signal color and controller type using interface-based polymorphism.




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




