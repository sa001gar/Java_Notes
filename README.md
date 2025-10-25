<span style="display:none">[^2_1][^2_10][^2_2][^2_3][^2_4][^2_5][^2_6][^2_7][^2_8][^2_9]</span>

[^2_1]: https://github.com/imranxc/java-basics-to-advanced

[^2_2]: https://github.com/Suryakant-Bharti/Important-Java-Concepts

[^2_3]: https://github.com/learning-zone/java-basics

[^2_4]: https://github.com/krishnasagrawal/Java-Programming-Notes

[^2_5]: https://github.com/cM2908/core-java-notes

[^2_6]: https://techaffinity.com/blog/oops-concepts-in-java/

[^2_7]: https://www.scribd.com/document/6934243/java-database-programming-with-jdbc

[^2_8]: https://github.com/aditya-shri/Java

[^2_9]: https://www.designgurus.io/blog/object-oriented-programming-oop

[^2_10]: https://www.scribd.com/document/265327667/Java-Database-Programming-With-JDBC


# Java Notes – Part 1: Core Java Foundations

## Table of Contents

1. Introduction to Java Architecture and Features
2. JVM, JRE, and JDK
3. Java vs C++
4. Compilation and Execution Process
5. Variables, Data Types, Operators, Control Flow, and Methods

***

## 1️⃣ Introduction to Java Architecture and Features

### Definition
Java is a **platform‑independent, object‑oriented, high‑level programming language** developed by Sun Microsystems (now Oracle). It follows WORA – “Write Once, Run Anywhere”.

### Real‑Life Analogy
Think of Java like a courier company: you give it a parcel (your program), it packs it into a universal box (*bytecode*) that can be delivered safely anywhere in the world, regardless of the country (platform).

### Core Components of Java Architecture

```
+-------------------------------------------+
|                 Java Code (.java)         |
+-------------------------------------------+
                     |
                     v
+-------------------------------------------+
| Java Compiler (javac) -> Bytecode (.class)|
+-------------------------------------------+
                     |
                     v
+-------------------------------------------+
| JVM (Class Loader + Runtime + GC + JNI)   |
+-------------------------------------------+
```

**Components**[^3_1][^3_2]

- **Class Loader:** Loads `.class` files into memory.
- **Method Area:** Stores class structures \& static data.
- **Heap:** Stores objects dynamically created at runtime.
- **Stack:** Holds local variables and method calls for each thread.
- **Execution Engine:** Includes Interpreter + JIT Compiler.
- **Garbage Collector:** Automatically frees unused memory.
- **JNI \& Native Libraries:** Allow interaction with non‑Java code.

### Key Java Features

- Platform independent (runs on JVM)
- Object‑oriented
- Robust and secure (no manual memory handling)
- Architecture‑neutral \& portable
- Multithreaded for parallel tasks
- High performance (JIT optimization)
- Dynamic and distributed (network APIs built in)

### Why Needed in Real Life
Used for developing banking systems, Android apps, enterprise backend servers, and IoT devices due to its portability and security.

***

## 2️⃣ JVM, JRE and JDK

### Definitions and Differences[^3_3]


| Aspect | JDK (Java Development Kit) | JRE (Java Runtime Environment) | JVM (Java Virtual Machine) |
| :-- | :-- | :-- | :-- |
| Purpose | For development (compiles and runs apps) | For running compiled apps | Executes bytecode runtime |
| Contains | JRE + compiler + tools | JVM + libraries | Execution engine only |
| Platform | Dependent | Dependent | Independent |
| Tools | javac, java, jar, javadoc, jdb | Class libraries, runtime libs | Interpreter, JIT compiler |

### ASCII Diagram

```
+-----------------------------------+
|     JDK (Developers use this)     |
|  +-----------------------------+  |
|  | JRE                        |  |
|  |  +-----------------------+  |  |
|  |  | JVM (Executes Bytecode)| |  |
|  |  +-----------------------+  |  |
|  +-----------------------------+  |
+-----------------------------------+
```

### Why Needed in Real Life
The JDK provides the environment and tools to write, compile, and run Java apps across operating systems—critical for cross‑platform development.

***

## 3️⃣ Java vs C++ Comparison

### Table of Key Differences[^3_4]


| Aspect | Java | C++ |
| :-- | :-- | :-- |
| Type | Pure OOP | Multi‑paradigm (OOP + Procedural) |
| Memory Management | Automatic (Garbage Collection) | Manual, uses pointers |
| Platform Dependency | Platform independent (JVM) | Platform dependent |
| Multiple Inheritance | Via interfaces only | Direct support |
| Execution Speed | Slightly slower | Generally faster |
| Syntax | Simpler (no header files) | Complex with templates |
| Security | High (no memory access) | Lower (pointer based) |
| Use Cases | Apps, web, mobile | System software, games |

### Why Java is Preferred
For enterprise applications, Java reduces bugs and ensures safer memory handling while maintaining readability and portability across platforms.

***

## 4️⃣ Compilation and Execution Process

### Steps[^3_5]
1. **Write Source Code:** Create a `.java` file.
2. **Compile:** `javac MyClass.java` → creates `MyClass.class` (bytecode).
3. **Execute:** `java MyClass` → JVM starts, loads bytecode, interprets or JIT‑compiles it.

### ASCII Flow

```
Source Code (.java)
       |
    [javac]
       |
  Bytecode (.class)
       |
    [java JVM]
       |
 Machine Execution
```

### Runnable Example

```java
// HelloWorld.java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Java World!");
    }
}
```

**Execution**

```bash
javac HelloWorld.java
java HelloWorld
```

**Output**

```
Hello, Java World!
```

**Exam Tip:** `.java` → `.class` → JVM execution is a frequently asked theory question; always mention bytecode’s role in platform independence.

***

## 5️⃣ Variables, Data Types, Operators, Control Flow and Methods

### Variables and Data Types[^3_6]
Java uses statically typed variables—each declared with a specific type.


| Category | Type | Example |
| :-- | :-- | :-- |
| Integer | byte, short, int, long | `int count = 10;` |
| Floating | float, double | `double pi = 3.14;` |
| Character | char | `char grade = 'A';` |
| Boolean | boolean | `boolean active = true;` |

### Operators
Arithmetic (+, −, *, /, %), Relational (>, ==), Logical (\&\&, ||, !), Assignment (=, +=).

### Control Flow

```java
if(balance < 1000) {
    System.out.println("Low Balance Warning!");
} else {
    System.out.println("Sufficient Balance.");
}
```

### Loops

```java
for(int i=1; i<=3; i++) {
    System.out.println("Transaction " + i);
}
```

Output:

```
Transaction 1
Transaction 2
Transaction 3
```

### Methods (Reusable Logic)

```java
public class BankAccount {
    double balance;

    // deposit method
    void deposit(double amount) {
        balance += amount; // add to balance
    }

    // method returning balance
    double getBalance() {
        return balance;
    }

    public static void main(String[] args) {
        BankAccount acc = new BankAccount();
        acc.deposit(500);
        System.out.println("Current Balance: " + acc.getBalance());
    }
}
```

**Output**

```
Current Balance: 500.0
```

### Why It Matters
Variables represent data states; control statements and loops bring decision‑making into programs like ATM systems or student management software.

***

## 📘 Quick Revision Summary

| Topic | Key Points |
| :-- | :-- |
| Architecture | JVM = Class Loader + Heap + Stack + Execution Engine + GC |
| JDK/JRE/JVM | JDK = JRE + Tools; JRE = JVM + Libs; JVM = Runs Bytecode |
| Java vs C++ | Java is managed, secure, and portable; C++ is faster but riskier |
| Compilation Cycle | .java → Javac → .class → JVM → Machine Code |
| Core Syntax | Variables, Types, Control Flow, Methods = logic foundation |

*Next Module → Part 2: Arrays, Strings \& I/O will cover 1D/2D arrays, String classes, immutability, Scanner, and File Streams using real‑world examples.*
<span style="display:none">[^3_10][^3_7][^3_8][^3_9]</span>

***

[^3_1]: https://www.interviewbit.com/blog/java-architecture/

[^3_2]: https://www.upgrad.com/blog/java-architecture-components-explained/

[^3_3]: https://www.tutorialspoint.com/java/java-jdk-jre-jvm.htm

[^3_4]: https://www.octalsoftware.com/blog/java-vs-c

[^3_5]: https://dev.to/imkrunalkanojiya/java-compilation-from-source-code-to-bytecode-execution-12hp

[^3_6]: https://www.msuniv.ac.in/images/distance

[^3_7]: https://www.edureka.co/blog/java-architecture/

[^3_8]: https://www.geekster.in/articles/java-architecture/

[^3_9]: https://vfunction.com/blog/java-architecture/

[^3_10]: https://www.geeksforgeeks.org/java/introduction-to-java/


---
# Java Notes – Part 2: Arrays, Strings \& I/O

## Table of Contents

1. Arrays (One‑dimensional and Two‑dimensional)
2. Strings (String class, StringBuffer, StringBuilder)
3. Immutability Concept
4. Scanner Class (Input)
5. File Input/Output (Byte and Character Streams)

***

## 1️⃣ Arrays

### Definition[^4_1][^4_7]
An **array** is a collection of similar data types stored in contiguous memory locations. Arrays allow indexing access and efficient traversal.

### Real‑Life Analogy
Imagine a row of lockers, each labeled with an index number. Every locker stores one value of the same type—like account balances of all customers.

### One‑Dimensional Array

```java
// Program: Tracking daily account balances
public class DailyBalance {
    public static void main(String[] args) {
        double[] balances = {1000.5, 1200.0, 950.75, 1320.0}; // declare & initialize
        double total = 0;

        // loop through array
        for (int i = 0; i < balances.length; i++) {
            total += balances[i]; // add to total
            System.out.println("Day " + (i + 1) + " Balance: " + balances[i]);
        }

        double avg = total / balances.length;
        System.out.println("Average Balance = " + avg);
    }
}
```

**Output**

```
Day 1 Balance: 1000.5  
Day 2 Balance: 1200.0  
Day 3 Balance: 950.75  
Day 4 Balance: 1320.0  
Average Balance = 1117.8125
```

### Two‑Dimensional Array (Matrix Example)

```java
// TransactionMatrix.java
public class TransactionMatrix {
    public static void main(String[] args) {
        int[][] transactions = {
            {100, 200, 150},
            {300, 250, 400},
            {500, 100, 50}
        };

        for (int i = 0; i < transactions.length; i++) {
            for (int j = 0; j < transactions[i].length; j++) {
                System.out.print(transactions[i][j] + "\t");
            }
            System.out.println();
        }
    }
}
```

**Output**

```
100 200 150  
300 250 400  
500 100 50
```

### Why Needed in Real Life
Arrays are ideal for storing bulk data like transaction logs, student marks, sensor readings, etc.

***

## 2️⃣ Strings

### Definition and Immutability[^4_7]
A **String** is a sequence of characters enclosed in double quotes like `"Hello"`. Strings in Java are immutable — once created, they cannot be changed.

```java
public class StringDemo {
    public static void main(String[] args) {
        String msg = "Welcome";
        String newMsg = msg.concat(" to Java");
        System.out.println(msg);       // original remains unchanged
        System.out.println(newMsg);    // new object created
    }
}
```

**Output**

```
Welcome  
Welcome to Java
```

### StringBuffer (vs String)
Used for **mutable strings**, especially in multi‑threaded environments.

```java
public class StringBufferDemo {
    public static void main(String[] args) {
        StringBuffer sb = new StringBuffer("Bank");
        sb.append(" Account");
        System.out.println(sb);
    }
}
```

**Output**

```
Bank Account
```

### StringBuilder
Same as `StringBuffer` but faster (not thread‑safe). Use for single‑threaded operations.

### Key Difference Table


| Aspect | String | StringBuffer | StringBuilder |
| :-- | :-- | :-- | :-- |
| Mutability | Immutable | Mutable | Mutable |
| Thread Safety | Safe (Synchronized) | Safe | Not Safe |
| Speed | Slow | Moderate | Fast |
| Use Case | Fixed values | Concurrent mods | Performance critical |

### Why Needed in Real Life
Strings handle names, messages, and file paths in apps. StringBuffer/StringBuilder help when dynamic text changes (e.g., bank statements generation).

***

## 3️⃣ Scanner Class (Input)

### Purpose and Usage[^4_2]
The `Scanner` class (from `java.util`) simplifies reading user inputs from console or files.

```java
import java.util.Scanner;

public class ATMInput {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter withdrawal amount: ");
        double amount = sc.nextDouble();
        System.out.println("Processing withdrawal of ₹" + amount);
        sc.close();
    }
}
```

**Output**

```
Enter withdrawal amount: 5000  
Processing withdrawal of ₹5000.0
```

**Exam Tip:** Mention `nextLine()`, `nextInt()`, `nextDouble()` used for different data types.

***

## 4️⃣ File I/O (Streams)

### Concept Flow

```
     +-----------+        +---------------+        +-------------+
     |  Program  | <----> | Stream (pipe) | <----> | File/Device |
     +-----------+        +---------------+        +-------------+
```

### Byte Streams
Used for binary data (images, audio).

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class CopyFile {
    public static void main(String[] args) throws IOException {
        FileInputStream fin  = new FileInputStream("input.txt");
        FileOutputStream fout = new FileOutputStream("output.txt");
        int b;
        while ((b = fin.read()) != -1) {
            fout.write(b);
        }
        fin.close();
        fout.close();
        System.out.println("File copied successfully!");
    }
}
```

**Output**

```
File copied successfully!
```

### Character Streams
Efficient for text I/O.

```java
import java.io.FileReader;
import java.io.FileWriter;

public class FileReadWrite {
    public static void main(String[] args) throws Exception {
        FileWriter fw = new FileWriter("notes.txt");
        fw.write("Java I/O concepts made easy!");
        fw.close();

        FileReader fr = new FileReader("notes.txt");
        int ch;
        while ((ch = fr.read()) != -1) {
            System.out.print((char) ch);
        }
        fr.close();
    }
}
```

**Output**

```
Java I/O concepts made easy!
```

### Why Needed in Real Life
Used to store and retrieve data from files like transaction reports, logs, or user profiles on disk.

***

## 📘 Quick Revision Summary

| Topic | Key Points |
| :-- | :-- |
| Arrays | Store fixed collection of same type elements |
| 1D vs 2D | Linear vs Table storage mode |
| Strings | Immutable |
| StringBuffer/Builder | Mutable and dynamic |
| Scanner | Used to take user input |
| File I/O | Byte Streams = binary, Character Streams = text |


***

*Next Module → Part 3: Object‑Oriented Programming (OOP) Fundamentals: Classes, Objects, Constructors, this, Overloading, Encapsulation, Inheritance, and Polymorphism.*
<span style="display:none">[^4_10][^4_3][^4_4][^4_5][^4_6][^4_8][^4_9]</span>


[^4_1]: https://www.geeksforgeeks.org/java/java-data-types/

[^4_2]: https://www.w3schools.com/java/java_variables.asp

[^4_3]: https://www.geeksforgeeks.org/java/operators-in-java/

[^4_4]: https://www.w3schools.com/java/java_operators.asp

[^4_5]: https://www.programiz.com/java-programming/operators

[^4_6]: https://www.slideshare.net/slideshow/java-variables-and-operators-55602182/55602182

[^4_7]: https://www.w3schools.com/java/java_data_types.asp

[^4_8]: https://www.scribd.com/document/545309002/oop-prese

[^4_9]: https://www.freecodecamp.org/news/java-data-types-and-variables/

[^4_10]: https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html


---


# Java Notes – Part 3: Object-Oriented Programming (OOP) Fundamentals

## Table of Contents

1. Class and Object
2. Constructor and this Keyword
3. Method Overloading
4. Static vs Instance Members
5. Encapsulation
6. Inheritance
7. Polymorphism
8. Abstraction

***

## 1️⃣ Class and Object

### Definition

- **Class:** Blueprint or template to create objects; defines properties (fields) and behaviors (methods).
- **Object:** Instance of a class representing a real-world entity with state and behavior.


### Real-life Analogy

A *class* is like a blueprint of a *car*. Individual cars made from that blueprint (Toyota, Honda) are *objects*. Each car has its own color, model, and state.

### Example

```java
// Vehicle.java
public class Vehicle {
    // Fields (properties)
    String brand;
    int year;

    // Method (behavior)
    void displayInfo() {
        System.out.println("Brand: " + brand + ", Year: " + year);
    }

    public static void main(String[] args) {
        Vehicle car = new Vehicle();  // Creating object
        car.brand = "Toyota";         // Setting property
        car.year = 2022;
        car.displayInfo();            // Calling method
    }
}
```

**Output**

```
Brand: Toyota, Year: 2022
```


### Key Takeaways

- Classes define structure; objects hold actual data.
- Objects interact by calling methods.

***

## 2️⃣ Constructor and this Keyword

### Constructor

A special method used to initialize objects when created. It has the same name as the class and no return type.

### this Keyword

Used to refer to the current object’s fields or methods, useful to resolve naming conflicts.

### Example

```java
public class BankAccount {
    String accountHolder;
    double balance;

    // Constructor to initialize
    BankAccount(String accountHolder, double balance) {
        this.accountHolder = accountHolder;  // this resolves field vs parameter conflict
        this.balance = balance;
    }

    void display() {
        System.out.println(accountHolder + "'s Balance: ₹" + balance);
    }

    public static void main(String[] args) {
        BankAccount acc = new BankAccount("Alice", 5000);
        acc.display();
    }
}
```

**Output**

```
Alice's Balance: ₹5000.0
```


### Why Needed

Constructors simplify the object creation process, ensuring fields are initialized properly.

***

## 3️⃣ Method Overloading

### Definition

Multiple methods in the same class with the same name but different parameter lists (signature).

### Example

```java
public class Calculator {
    int add(int a, int b) {
        return a + b;
    }
    double add(double a, double b) {
        return a + b;
    }
    int add(int a, int b, int c) {
        return a + b + c;
    }

    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.add(10, 20));      // Calls first method
        System.out.println(calc.add(5.5, 3.2));    // Calls second method
        System.out.println(calc.add(1, 2, 3));     // Calls third method
    }
}
```

**Output**

```
30  
8.7  
6
```


### Why Needed

Allows flexibility, improving readability by using the same method name for related actions.

***

## 4️⃣ Static vs Instance Members

| Feature | Instance Members | Static Members |
| :-- | :-- | :-- |
| Belongs to | Object (each object has own copy) | Class (shared across all objects) |
| Access using | Object reference | Class name directly or object |
| Use case | Unique data per object | Shared data or utility methods |

### Example

```java
public class Student {
    String name;                    // instance variable
    static String school = "ABC School";  // static variable

    void display() {
        System.out.println(name + " studies in " + school);
    }

    public static void main(String[] args) {
        Student s1 = new Student();
        s1.name = "John";
        s1.display();

        Student s2 = new Student();
        s2.name = "Alice";
        s2.display();

        System.out.println(Student.school);  // Access static member via class
    }
}
```

**Output**

```
John studies in ABC School  
Alice studies in ABC School  
ABC School
```


***

## 5️⃣ Encapsulation

### Definition

Hiding internal state and requiring all interaction to be performed through methods (getters/setters). Protects data from unauthorized access.

### Real-life Analogy

A bank account hides the balance and allows deposit/withdrawal through defined methods only.

### Example

```java
public class Account {
    private double balance;  // private field

    // Getter
    public double getBalance() {
        return balance;
    }

    // Setter with validation
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        } else {
            System.out.println("Invalid amount");
        }
    }

    public static void main(String[] args) {
        Account acc = new Account();
        acc.deposit(1000);
        System.out.println("Balance: ₹" + acc.getBalance());
    }
}
```

**Output**

```
Balance: ₹1000.0
```


### Why Needed

Protects sensitive data and provides control over data manipulations.

***

## 6️⃣ Inheritance

### Definition

Mechanism where one class (child) inherits fields and methods of another class (parent).

### Real-life Analogy

A Vehicle class generalizes characteristics, a Car class inherits and adds its specific details.

### Example

```java
class Vehicle {
    void start() {
        System.out.println("Vehicle started.");
    }
}

class Car extends Vehicle {
    void openDoor() {
        System.out.println("Car door opened.");
    }

    public static void main(String[] args) {
        Car myCar = new Car();
        myCar.start();      // Inherited method
        myCar.openDoor();   // Own method
    }
}
```

**Output**

```
Vehicle started.  
Car door opened.
```


***

## 7️⃣ Polymorphism

### Definition

Ability of one object to take many forms. In Java, mainly includes method overriding and method overloading.

### Real-life Analogy

A dog can be trained to bark, guard, or fetch — same dog, different behaviors based on context.

### Example (Overriding)

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }

    public static void main(String[] args) {
        Animal a = new Dog();
        a.sound();  // Calls overridden method in Dog
    }
}
```

**Output**

```
Dog barks
```


***

## 8️⃣ Abstraction

### Definition

Hiding complex implementation details and showing only essential features.

### Real-life Analogy

Driving a car — you interact with the steering wheel and pedals without needing to know engine inner workings.

### Example

```java
abstract class ATM {
    abstract void withdraw(double amount);

    void welcomeMsg() {
        System.out.println("Welcome to ATM!");
    }
}

class BankATM extends ATM {
    void withdraw(double amount) {
        System.out.println("Withdrawn: ₹" + amount);
    }

    public static void main(String[] args) {
        BankATM atm = new BankATM();
        atm.welcomeMsg();
        atm.withdraw(5000);
    }
}
```

**Output**

```
Welcome to ATM!  
Withdrawn: ₹5000
```


***

## 📘 Quick Revision Summary

| Concept | Description | Example Class |
| :-- | :-- | :-- |
| Class \& Object | Blueprint and instance | Vehicle |
| Constructor | Initializes new object | BankAccount |
| Method Overloading | Same method name, different parameters | Calculator |
| Static vs Instance | Shared vs unique copy | Student |
| Encapsulation | Data hiding with private + getter/setter | Account |
| Inheritance | "Is-a" relationship, reuse code | Vehicle → Car |
| Polymorphism | Many forms, method overriding | Animal → Dog |
| Abstraction | Hide complexity through abstract classes | ATM, BankATM |


***

*Next Module → Part 4: Advanced OOP (Inheritance, Interfaces, Packages), Garbage Collection, Wrapper Classes, Autoboxing, and Enums.*
<span style="display:none">[^5_1][^5_10][^5_2][^5_3][^5_4][^5_5][^5_6][^5_7][^5_8][^5_9]</span>


[^5_1]: https://www.geeksforgeeks.org/java/object-oriented-programming-oops-concept-in-java/

[^5_2]: https://www.w3schools.com/java/java_oop.asp

[^5_3]: https://www.srividyaengg.ac.in/coursematerial/CSE/104341.pdf

[^5_4]: https://www.freecodecamp.org/news/learn-java-object-oriented-programming/

[^5_5]: https://www.freecodecamp.org/news/object-oriented-programming-concepts-java/

[^5_6]: https://raygun.com/blog/oop-concepts-java/

[^5_7]: https://www.youtube.com/watch?v=LarQG8Leqbo

[^5_8]: https://www.coursera.org/learn/object-oriented-program-in-java

[^5_9]: https://docs.oracle.com/javase/tutorial/java/concepts

[^5_10]: https://www.baeldung.com/java-oop


---


# Java Notes – Part 4: Advanced OOP and Exception Handling

## Table of Contents
1. Inheritance (Deep Dive – Single, Multilevel, Overriding)
2. Abstract Classes and Interfaces
3. Packages and Access Modifiers
4. Wrapper Classes and Autoboxing/Unboxing
5. Enumerations and Metadata (Annotations)
6. Garbage Collection
7. Exception Handling

***

## 1️⃣ Inheritance (Deep Dive)

### Single and Multilevel Inheritance[^6_11]

```java
class Vehicle {
    void start() { System.out.println("Vehicle starts..."); }
}
class Car extends Vehicle {
    void drive() { System.out.println("Car is driving..."); }
}
class ElectricCar extends Car {
    void charge() { System.out.println("Car charging..."); }
    public static void main(String[] args) {
        ElectricCar e = new ElectricCar();
        e.start();   // inherited
        e.drive();   // inherited
        e.charge();  // own
    }
}
```

**Output**

```
Vehicle starts...
Car is driving...
Car charging...
```

### Method Overriding
When a child class redefines a parent method with the same signature.

```java
class Parent { void greet(){ System.out.println("Hello from Parent!"); } }
class Child extends Parent {
    @Override void greet(){ System.out.println("Hello from Child!"); }
    public static void main(String[] args){
        Parent p = new Child();
        p.greet(); // runtime polymorphism
    }
}
```

**Output**

```
Hello from Child!
```

### Why Needed
Encourages code reuse and specialization for different subclasses (like Vehicle → Car → EV).

***

## 2️⃣ Abstract Classes and Interfaces

### Abstract Class
Cannot be instantiated; can contain both abstract and concrete methods.

```java
abstract class Account {
    abstract void withdraw(double amount);
    void welcome(){ System.out.println("Welcome to Our Bank!"); }
}
class SavingsAccount extends Account {
    void withdraw(double amount){ System.out.println("Withdrawn ₹" + amount); }
    public static void main(String[] args){
        SavingsAccount s = new SavingsAccount();
        s.welcome();
        s.withdraw(2000);
    }
}
```

**Output**

```
Welcome to Our Bank!
Withdrawn ₹2000
```

### Interface
Pure abstraction (only method declarations and constants until Java 8 added default methods).

```java
interface ATM {
    void withdraw(double amt);
}
class HDFCATM implements ATM {
    public void withdraw(double amt){ System.out.println("Dispensing ₹" + amt); }
    public static void main(String[] args){
        ATM atm = new HDFCATM();
        atm.withdraw(5000);
    }
}
```

**Output**

```
Dispensing ₹5000
```

### Abstract vs Interface


| Aspect | Abstract Class | Interface |
| :-- | :-- | :-- |
| Contains | Abstract + Concrete methods | Abstract (default, static allowed) |
| Inheritance | Single | Multiple |
| Constructor | Yes | No |
| Use When | “is‑a” relation + shared state | Common behavior across unrelated classes |


***

## 3️⃣ Packages and Access Modifiers

### Definition
Packages group related classes and interfaces; used to avoid naming conflicts and assist modularization.

```java
package banking;                 // in file: banking/Account.java
public class Account {
    public void display() {
        System.out.println("Bank account details...");
    }
}
```

**Access from another file**

```java
import banking.Account;
public class MainBank {
    public static void main(String[] args) {
        Account acc = new Account();
        acc.display();
    }
}
```

### Access Modifiers


| Modifier | Scope |
| :-- | :-- |
| public | Accessible everywhere |
| protected | Same package + subclasses |
| default (no modifier) | Same package only |
| private | Same class only |


***

## 4️⃣ Wrapper Classes and Autoboxing[^6_11]
Java wraps primitive types in object classes inside `java.lang`.


| Primitive | Wrapper |
| :-- | :-- |
| int | Integer |
| double | Double |
| char | Character |
| boolean | Boolean |

### Autoboxing and Unboxing

```java
public class WrapperDemo {
    public static void main(String[] args) {
        int n = 10;
        Integer obj = n; // Autoboxing
        int m = obj;     // Unboxing
        System.out.println("Sum: " + (n + m));
    }
}
```

**Output**

```
Sum: 20
```

### Why Needed
Wrapper classes allow primitives to be used as objects (e.g., in collections like ArrayList or Maps).

***

## 5️⃣ Enumerations and Metadata (Annotations)
### Enum
A special class for fixed constants.

```java
enum TransactionStatus {
    PENDING, COMPLETED, FAILED
}
public class Payment {
    public static void main(String[] args) {
        TransactionStatus status = TransactionStatus.COMPLETED;
        System.out.println("Payment " + status);
    }
}
```

**Output**

```
Payment COMPLETED
```

### Annotation (Metadata)
Provides information to the compiler or runtime.

```java
@interface Author {
    String name();
}
@Author(name="John Doe")
public class Report {
    public static void main(String[] args) {
        System.out.println("Annotation example executed");
    }
}
```


***

## 6️⃣ Garbage Collection

### Definition
Process by which JVM automatically frees up memory by destroying unused objects.

### ASCII Flow

```
   +--------------+        +----------------+
   | Active Heap  | -----> | Unreferenced   |
   +--------------+        +----------------+
            |                     |
            v                     v
       Garbage Collector --> Deletes Objects
```

### Usage Hint
Force collection (using for demo only):

```java
System.gc(); // requests GC
```

### Why Needed
Eliminates manual memory management bugs like memory leaks or dangling pointers.

***

## 7️⃣ Exception Handling

### Definition and Keywords[^6_6][^6_9]
An **exception** is an unexpected event during execution that disrupts the normal flow of program instructions.

**Keywords:**

- `try`: Wraps code that might throw an exception.
- `catch`: Handles the exception if it occurs.
- `throw`: Manually raise an exception.
- `throws`: Declares potential exceptions a method might throw.
- `finally`: Executes regardless of whether an exception occurs.

### Example – Try‑Catch‑Finally[^6_4]

```java
public class ExceptionDemo {
    public static void main(String[] args) {
        try {
            int result = 10 / 0;  // Throws ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage());
        } finally {
            System.out.println("This block always executes.");
        }
    }
}
```

**Output**

```
Error: / by zero
This block always executes.
```

### Custom Exception

```java
class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String msg){ super(msg); }
}
class Bank {
    double balance = 1000;
    void withdraw(double amt) throws InsufficientFundsException {
        if(amt > balance)
            throw new InsufficientFundsException("Insufficient balance!");
        balance -= amt;
    }
    public static void main(String[] args){
        Bank b = new Bank();
        try{
            b.withdraw(2000);
        }catch(InsufficientFundsException e){
            System.out.println(e.getMessage());
        }
    }
}
```

**Output**

```
Insufficient balance!
```

### Exam Tip
- Mention the five keywords and their flow.
- Every `try` needs at least one `catch` or `finally`.

***

## 📘 Quick Revision Summary


| Concept | Purpose |
| :-- | :-- |
| Inheritance | Code reuse and specialization |
| Abstract Class / Interface | Abstraction and polymorphism |
| Packages | Organize and protect code |
| Wrapper Classes | Object representation of primitives |
| Enums | Predefined constants |
| Garbage Collection | Automatic memory cleanup |
| Exceptions | Graceful error handling |


***

*Next Module → Part 5: Threads, Networking, JDBC, Applets \& Event Handling — featuring lifecycles, synchronization flow, TCP/UDP, database connectivity, and AWT GUI.*
<span style="display:none">[^6_1][^6_10][^6_2][^6_3][^6_5][^6_7][^6_8]</span>


[^6_1]: https://www.w3schools.com/java/java_try_catch.asp

[^6_2]: https://www.geeksforgeeks.org/java/flow-control-in-try-catch-finally-in-java/

[^6_3]: https://www.scaler.com/topics/java/try-catch-and-finally-in-java/

[^6_4]: https://www.educative.io/answers/how-to-use-the-try-catch-and-finally-blocks-in-java

[^6_5]: https://www.ibm.com/docs/en/dbaoc?topic=actions-exception-handling-statements

[^6_6]: https://www.scholarhat.com/tutorial/java/exception-handling-in-java

[^6_7]: https://jenkov.com/tutorials/java-exception-handling/basic-try-catch-finally.html

[^6_8]: https://www.programiz.com/java-programming/exception-handling

[^6_9]: https://www.geeksforgeeks.org/java/exceptions-in-java/

[^6_10]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch

[^6_11]: https://www.geeksforgeeks.org/java/object-oriented-programming-oops-concept-in-java/


---


# Java Notes – Part 5: Threads, Networking, JDBC, Applets \& Event Handling

## Table of Contents
1. Multithreading in Java
2. Thread Class \& Runnable Interface
3. Thread Lifecycle and Synchronization
4. Networking Basics (TCP/UDP)
5. JDBC Connectivity Steps
6. Applets and AWT GUI
7. Event Handling and Adapter Classes

***

## 1️⃣ Multithreading in Java

### Definition
Multithreading allows concurrent execution of multiple parts (threads) of a program to maximize CPU efficiency and performance.

### Real‑life Analogy
Think of an ATM center with many machines. Each machine is a thread serving different users simultaneously. All access the same central database.

### Thread Creation Methods
**(1) By extending `Thread` class**

```java
class ATMThread extends Thread {
    public void run() {
        System.out.println("ATM Transaction in progress by " + Thread.currentThread().getName());
    }
    public static void main(String[] args) {
        ATMThread user1 = new ATMThread();
        ATMThread user2 = new ATMThread();
        user1.start();
        user2.start();
    }
}
```

**Output**

```
ATM Transaction in progress by Thread‑0  
ATM Transaction in progress by Thread‑1
```

**(2) By implementing `Runnable` interface**

```java
class DepositTask implements Runnable {
    public void run() {
        System.out.println("Depositing Money...");
    }
    public static void main(String[] args) {
        Thread t = new Thread(new DepositTask());
        t.start();
    }
}
```

**Why Needed**
Improves program responsiveness and handles multiple tasks (e.g., downloads or users) in parallel.

***

## 2️⃣ Thread Lifecycle and Synchronization

### Thread States

```
NEW → RUNNABLE → RUNNING → BLOCKED/WAITING → TERMINATED
```

### Synchronization (Prevent Race Conditions)

```java
class Account {
    private int balance = 1000;
    synchronized void withdraw(int amount) {
        if (balance >= amount) {
            System.out.println(Thread.currentThread().getName() + " withdrawing " + amount);
            balance -= amount;
            System.out.println("Remaining balance: " + balance);
        } else System.out.println("Insufficient funds!");
    }
}

public class BankSync {
    public static void main(String[] args) {
        Account acc = new Account();
        Thread t1 = new Thread(() -> acc.withdraw(700), "User‑1");
        Thread t2 = new Thread(() -> acc.withdraw(500), "User‑2");
        t1.start();
        t2.start();
    }
}
```

**Sample Output**

```
User‑1 withdrawing 700  
Remaining balance: 300  
Insufficient funds!
```

### Why Needed
Ensures data consistency when multiple threads access shared resources.

***

## 3️⃣ Networking Basics (TCP/UDP)

### Definition and Packages
Networking in Java enables communication between devices using classes in `java.net`.

**Core Classes**
- `Socket` and `ServerSocket` – for TCP
- `DatagramSocket` and `DatagramPacket` – for UDP

### Example – Simple TCP Communication

**Server.java**

```java
import java.net.*;
import java.io.*;
public class Server {
    public static void main(String[] args) throws Exception {
        ServerSocket ss = new ServerSocket(5000);
        Socket s = ss.accept();
        DataInputStream dis = new DataInputStream(s.getInputStream());
        String msg = dis.readUTF();
        System.out.println("Client: " + msg);
        ss.close();
    }
}
```

**Client.java**

```java
import java.net.*;
import java.io.*;
public class Client {
    public static void main(String[] args) throws Exception {
        Socket s = new Socket("localhost", 5000);
        DataOutputStream dos = new DataOutputStream(s.getOutputStream());
        dos.writeUTF("Hello Server!");
        s.close();
    }
}
```

**Output**

```
Client: Hello Server!
```

### Why Needed
Used in chat applications, banking services, IoT devices, and client‑server systems.

***

## 4️⃣ JDBC (Java Database Connectivity)

### Definition 
A Java API to connect and execute queries with databases (e.g., MySQL or Oracle).

### JDBC Workflow ASCII Diagram [similar to SQL flow]

```
Application → DriverManager → Connection → Statement → ResultSet
```

### Five Core Steps
1. **Load Driver**
2. **Establish Connection**
3. **Create Statement**
4. **Execute Query**
5. **Close Connection**

### Example (with MySQL)

```java
import java.sql.*;
public class JDBCExample {
    public static void main(String[] args) {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");  // Step 1: Load driver
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/bankdb", "root", "password"); // Step 2
            Statement stmt = con.createStatement();   // Step 3
            ResultSet rs = stmt.executeQuery("SELECT * FROM accounts"); // Step 4
            while (rs.next()) {
                System.out.println(rs.getInt(1) + " " + rs.getString(2));
            }
            con.close();  // Step 5
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output**

```
101 John  
102 Alice
```

### Why Needed
Links Java apps to backend databases for storing user data, transactions, payments, etc.

***

## 5️⃣ Applets and GUI (AWT)

### Definition
Applets are small Java programs that run within a browser or AppViewer and use the Abstract Window Toolkit (AWT) for GUI components like buttons and labels.

### Applet Lifecycle

```
init() → start() → paint() → stop() → destroy()
```

### Example (Applet)

```java
import java.applet.*;
import java.awt.*;

public class BankApplet extends Applet {
    public void paint(Graphics g) {
        g.drawString("Welcome to Banking Applet", 20, 20);
    }
}
```

**HTML to run**

```html
<applet code="BankApplet.class" width="300" height="100"></applet>
```

**Exam Tip:**
Always import `java.awt.*` and `java.applet.*`.
Paint method is like `main()` for applets.

***

## 6️⃣ Event Handling and Adapter Classes

### Event Handling Model (Delegation Model)
1. Event Source (button, textfield)
2. Event Listener (object handling action)
3. Event Object (carries details)

### Example – ActionListener

```java
import java.awt.*;
import java.awt.event.*;

public class ATMGUI extends Frame implements ActionListener {
    TextField tf;
    Button deposit;
    int balance = 1000;

    ATMGUI() {
        tf = new TextField();
        tf.setBounds(50, 50, 150, 20);
        deposit = new Button("Deposit ₹100");
        deposit.setBounds(60, 100, 100, 20);
        deposit.addActionListener(this);
        add(deposit); add(tf);
        setSize(250, 200);
        setLayout(null);
        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        balance += 100;
        tf.setText("Balance: " + balance);
    }

    public static void main(String[] args) {
        new ATMGUI();
    }
}
```

**Output**

```
GUI window with button -> clicking updates balance
```

### Adapter Classes
Used to avoid implementing all methods of listener interfaces.
E.g., `MouseAdapter`, `KeyAdapter`.

***

## 📘 Quick Revision Summary


| Concept | Purpose |
| :-- | :-- |
| Threading | Parallel execution of tasks |
| Synchronization | Avoid race conditions |
| Networking | Device→device communication |
| JDBC | Database connectivity |
| Applets/GUI | Graphical interface development |
| Event Handling | Respond to user actions |


***

✅ **End of Complete Java Notes Document**

This comprehensive file (Parts 1 – 5) now covers **every topic** in the requested sequence—from **Java architecture to threads, networking, and GUI/event handling.**
<span style="display:none">[^7_1][^7_10][^7_2][^7_3][^7_4][^7_5][^7_6][^7_7][^7_8][^7_9]</span>

<div align="center">⁂</div>

[^7_1]: https://www.geeksforgeeks.org/java/garbage-collection-in-java/

[^7_2]: https://newrelic.com/blog/best-practices/java-garbage-collection

[^7_3]: https://www.ibm.com/think/topics/garbage-collection-java

[^7_4]: https://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html

[^7_5]: https://www.eginnovations.com/blog/what-is-garbage-collection-java/

[^7_6]: https://www.logicmonitor.com/blog/garbage-collection-in-java

[^7_7]: https://dev.to/brilworks/garbage-collection-in-java-explained-8pg

[^7_8]: https://www.codecurated.com/blog/understanding-how-java-garbage-collector-works/

[^7_9]: https://www.dynatrace.com/resources/ebooks/javabook/how-garbage-collection-works/

[^7_10]: https://stackify.com/what-is-java-garbage-collection/

