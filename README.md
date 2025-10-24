# Java Complete Notes: 

Welcome to your all-in-one **Java Exam Preparation Notes**! This document covers every essential Java concept in the exact order you need, using beginner-friendly explanations, real-world examples, code with comments, diagrams, revision tips, and exam-focused summaries.

***

## Table of Contents

1. [Introduction to Java Architecture and Features](#introduction-to-java-architecture-and-features)
2. [JVM, JRE, JDK](#jvm-jre-jdk)
3. [Java vs C++](#java-vs-c)
4. [Compilation \& Execution](#compilation--execution)
5. [Variables, Data Types, Operators, Control Flow, Methods](#variables-data-types-operators-control-flow-methods)
6. [Arrays, Strings, and I/O](#arrays-strings-and-io)
    - [One/Two-dimensional arrays](#onetwo-dimensional-arrays)
    - [String class, StringBuffer, StringBuilder](#string-class-stringbuffer-stringbuilder)
    - [Immutability](#immutability)
    - [Scanner, File input/output, Streams](#scanner-file-inputoutput-streams)
7. [Object-Oriented Programming](#object-oriented-programming)
    - [Class, Object, Constructor, this keyword](#class-object-constructor-this-keyword)
    - [Method Overloading, Static vs Instance](#method-overloading-static-vs-instance)
    - [Encapsulation, Inheritance, Polymorphism, Abstraction](#encapsulation-inheritance-polymorphism-abstraction)
    - [Garbage Collection](#garbage-collection)
8. [Inheritance, Interfaces, Packages, Enumerations, Autoboxing, Metadata](#inheritance-interfaces-packages-enumerations-autoboxing-metadata)
    - [Single/Multilevel Inheritance, Method Overriding](#singlemultilevel-inheritance-method-overriding)
    - [Abstract classes, Interfaces, Package creation](#abstract-classes-interfaces-package-creation)
    - [java.lang, java.util, Wrapper Classes](#javalang-javautil-wrapper-classes)
    - [Autoboxing/Unboxing, Enums, Metadata](#autoboxingunboxing-enums-metadata)
9. [Exception Handling, Threading, Networking, JDBC](#exception-handling-threading-networking-jdbc)
    - [Types of exceptions, try-catch-finally, throw/throws, custom exceptions](#types-of-exceptions-try-catch-finally-throwthrows-custom-exceptions)
    - [Thread class, Runnable interface, Synchronization](#thread-class-runnable-interface-synchronization)
    - [Networking basics, TCP/UDP concepts](#networking-basics-tcpudp-concepts)
    - [JDBC connectivity steps with real example](#jdbc-connectivity-steps-with-real-example)
10. [Applets and Event Handling](#applets-and-event-handling)
    - [Applet lifecycle, GUI design using AWT](#applet-lifecycle-gui-design-using-awt)
    - [Event listener model](#event-listener-model)
    - [Inner classes and Adapter classes](#inner-classes-and-adapter-classes)

***

## Introduction to Java Architecture and Features

### What is Java?

Java is a high-level, object-oriented programming language invented by Sun Microsystems (now owned by Oracle), designed for WORA (“Write Once, Run Anywhere”).
**Analogy:** Think of Java as a universal translator: Write your message once, and anyone (any computer system) can read it with the help of a translator (the JVM).

- **Platform-independent:** Runs anywhere, thanks to the JVM.
- **Object-Oriented:** Encapsulates data and logic, mirroring real-world systems.
- **Robust \& Secure:** Manages memory and provides error handling.
- **Multithreaded:** Can handle many tasks simultaneously.
- **Distributed:** Supports networking and remote method invocation.
- **Rich API:** For GUI, utilities, data structures, networking, IO, and more.[^1][^2]

#### Why Java in Real Life?

Java is everywhere—from enterprise banking systems, mobile apps (Android), smartcards, ATMs, to web servers—because of its reliability, security, and portability.

#### Key Features (Summary Table)

| Feature | Description | Example Usage |
| :-- | :-- | :-- |
| Simple | C-like syntax; easy to learn | Similar to C++ |
| Platform-Independent | Runs on any OS with JVM | Windows, Linux, Mac |
| Object-Oriented | Organizes code via real-world entities | BankAccount class |
| Secure | Built-in security manager, no pointers | Web applications |
| Robust | Automatic memory management, exceptions | ATM, Banking Apps |
| Multithreaded | Performs multiple tasks at once | Chat servers |
| Distributed | Supports networking, RMI | Enterprise systems |

**Exam Tip:**
Java’s platform independence is achieved via **bytecode**—not source code portability.

***

## JVM, JRE, JDK

### Definitions

- **JVM (Java Virtual Machine):**
    - An engine that runs Java bytecode.
    - Ensures platform independence.
    - Performs Just-In-Time (JIT) compilation, garbage collection, and security checks.
- **JRE (Java Runtime Environment):**
    - JVM + libraries required to run Java programs.
    - Does **not** include development tools (like compilers).
- **JDK (Java Development Kit):**
    - JRE + development tools (javac, debugger, etc.).
    - Required for writing and compiling Java code.[^3][^4][^5][^6]


#### ASCII Diagram: JDK, JRE, JVM Structure

```
+---------------------------+
|        JDK                |
|  +---------------------+  |
|  |      JRE            |  |
|  |  +---------------+  |  |
|  |  |    JVM        |  |  |
|  |  +---------------+  |  |
|  +---------------------+  |
+---------------------------+
```


#### Why Needed in Real Life?

- Developers need **JDK** to write/compile Java code.
- End users/systems use **JRE** to run apps.
- **JVM** ensures one compiled program runs everywhere.


#### Revision

|  | Contains JVM | Contains Compiler | Run Code | Compile Code |
| :-- | :-- | :-- | :-- | :-- |
| JVM | Yes | No | Yes | No |
| JRE | Yes | No | Yes | No |
| JDK | Yes | Yes | Yes | Yes |


***

## Java vs C++

| Feature | Java | C++ |
| :-- | :-- | :-- |
| Platform independent | Yes (JVM runs everywhere) | No (platform-dependent executables) |
| Memory management | Automatic (Garbage Collection) | Manual (new/delete) |
| Multiple inheritance | No (uses interfaces) | Yes (using classes directly) |
| Pointers | Not exposed to programmer | Programmer has full control |
| Operator overloading | No | Yes |
| GUI support | Robust via libraries | Possible with additional frameworks |
| Syntax | C-like, stricter check | C language compatible |
| Speed | Slower (JVM overhead) | Faster (compiles to native) |
| Security | High (built-in checks) | Lower (pointer manipulation possible) |

#### Exam Insight

Java’s strong memory management and security make it a default language for enterprise and educational use.[^7][^8][^9][^10][^11]

#### Why such differences matter?

Java’s design targets safety and cross-platform deployment; C++ focuses on speed and low-level control (hardware programming, embedded systems).

***

## Compilation \& Execution

### Process Steps

1. Write code (`.java` file)
2. Compile (`javac`) → **Bytecode** (`.class` file)
3. Execute via `java` (JVM) → runs the bytecode on any OS[^12][^13][^14][^15][^16][^17]

#### ASCII Flowchart: Java Compilation \& Execution

```
Source Code (.java)
        |
    javac compiler
        |
    Bytecode (.class)
        |
    JVM (java command)
        |
    Output (runs on any OS)
```

**Real World Analogy:**
Think email attachments: You write a letter (source code), convert it into PDF (bytecode), and anyone with a PDF reader (JVM) can read it—on Windows, Mac, or mobile.

#### Code Example

```java
// Calculator.java
public class Calculator {
    public static void main(String[] args) {
        int a = 10, b = 20;
        System.out.println("Sum: " + (a + b));
    }
}
// Compile: javac Calculator.java
// Run:     java Calculator
// Output:
// Sum: 30
```

**Key Takeaway:**
Java code *never* runs directly on hardware; the JVM interprets/compiles the bytecode.[^13][^12]

***

## Variables, Data Types, Operators, Control Flow, Methods

### Variables \& Data Types

- **Primitive Types:** int, float, double, char, boolean, byte, short, long
- **Non-Primitive (Reference):** String, Arrays, Classes, Interfaces, Objects[^18][^19][^20][^21][^22][^23]

| Type | Size | Example |
| :-- | :-- | :-- |
| int | 4 byte | int age = 18; |
| char | 2 byte | char grade = 'A'; |
| boolean | 1 bit | boolean isATMActive = true; |

```java
// BankAccount.java
int balance = 500;   // integer
String holder = "Rahul";  // String (object)
char type = 'S';    // char
```


#### Why Different Types?

Storing different data precisely—like a Student's name (String) v/s marks (float).

#### Operators

- **Arithmetic:** +, -, *, /, %
- **Relational:** >, <, >=, <=, ==, !=
- **Logical:** \&\&, ||, !
- **Assignment:** =, +=, -=, etc.
- **Unary:** ++, --


### Control Flow

- **if, else, switch**
- **Loops:** for, while, do-while
- **Break/continue**

```java
// ATM eligibility check example
int balance = 1200;
if (balance > 1000) {
    System.out.println("Eligible for premium account.");
} else {
    System.out.println("Regular account.");
}
```


#### Why Needed?

Decision making and repetitive tasks (like ATM pin checks, menu systems).

### Methods

- Used to modularize code and promote reuse.
- Syntax:

```java
// Student management example
public int getGrade(int marks) {
    if (marks >= 90) return 'A';
    else if (marks >= 80) return 'B';
    else return 'C';
}
```

**Exam Tip:**
Define methods for each distinct operation for clean and testable code.

#### Quick Revision Table

| Control | Usage |
| :-- | :-- |
| if | Decision making |
| switch | Multi-branch decision |
| for | Known iterations |
| while | Unknown iterations |
| break | Exit from loop/block |


***

## Arrays, Strings, and I/O

### One/Two-dimensional Arrays

#### Definition

- **One-dimensional:** Linear, like a list—e.g., marks of a student.
- **Two-dimensional:** Matrix, like a table—e.g., marks of all students in all subjects.[^24][^25][^26][^27][^28][^29][^30]


#### Real-life analogy:

- **1D:** List of ATM transactions.
- **2D:** ATM transactions for multiple users (user × transaction).

```java
// 1D Array: Store account balances
int[] balances = {1000, 2000, 3000};

// 2D Array: Store marks of 3 students in 2 subjects
int[][] studentMarks = {
    {90, 80},
    {88, 76},
    {94, 92}
};
```


#### Output

```
System.out.println("Student 1, Subject 2: " + studentMarks[^0][^1]);
// Output: 80
```


#### Summary Table

| Array Type | Example | Access Syntax |
| :-- | :-- | :-- |
| 1D | int[] arr | arr |
| 2D | int[][] arr | arr[^1][^7] |


***

### String Class, StringBuffer, StringBuilder

#### Definition \& Need

- **String:** Immutable sequences of chars (e.g., account number, name)
- **StringBuffer:** Mutable, thread-safe (allows changes, safe for multithreading)
- **StringBuilder:** Mutable, NOT thread-safe (faster for single-thread)[^31][^32][^33][^34][^35][^36]


#### Real-World Analogy

- **String:** Like a permanent marker; once written, cannot erase.
- **StringBuffer:** Like a whiteboard with a lock (editable, safe for shared use).
- **StringBuilder:** Like a personal notepad (editable, but risky if shared).


#### Code Example

```java
// BankAccount String example
String accNo = "SB1001";
accNo.concat("99"); // doesn't change original String

StringBuffer sb = new StringBuffer("Rahul");
sb.append(" Sharma"); // changes the content

StringBuilder sbl = new StringBuilder("ATM");
sbl.append(" Machine");
```


#### Output

```
System.out.println(accNo);   // SB1001
System.out.println(sb);      // Rahul Sharma
System.out.println(sbl);     // ATM Machine
```


#### Summary Table

| Feature | String | StringBuffer | StringBuilder |
| :-- | :-- | :-- | :-- |
| Mutable | No | Yes | Yes |
| Thread-Safe | Yes | Yes | No |
| Performance | Average | Slower | Fastest |


***

### Immutability

- **String objects can't be changed after creation.**
- Guarantees **security**, memory efficiency via string pool, and thread safety.


#### Why Needed?

- E.g., banking transactions: ensures critical details can’t be changed accidentally.


#### Key Point

Whenever you modify a String, JVM creates a new object.

***

### Scanner, File Input/Output, Streams

#### Scanner

```java
import java.util.Scanner;
Scanner sc = new Scanner(System.in);
System.out.println("Enter balance:");
int balance = sc.nextInt();
```

**Output:**
User enters balance, system reads it.

#### File I/O (Storing Account Logs)

```java
import java.io.FileWriter;
import java.io.IOException;

public class WriteDemo {
    public static void main(String[] args) {
        try {
            FileWriter fw = new FileWriter("account.txt");
            fw.write("Balance: 5000");
            fw.close();
        } catch(IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
// Output: File 'account.txt' contains "Balance: 5000"
```

- **Streams:** Used for reading/writing bytes (binary data) and characters (text data).
    - Byte Streams: FileInputStream, FileOutputStream
    - Character Streams: FileReader, FileWriter

***

## Object-Oriented Programming

### Class, Object, Constructor, this Keyword

#### Class \& Object

- **Class:** Blueprint (e.g., BankAccount)
- **Object:** Real-world entity (e.g., Rahul’s bank a/c)

```java
// BankAccount class
public class BankAccount {
    String name;
    int balance;

    // Constructor
    public BankAccount(String name, int balance) {
        this.name = name; // 'this' distinguishes instance variable
        this.balance = balance;
    }
}
```


#### this Keyword

Distinguishes class fields from parameters with same name.

#### Why OOP?

- Models complex systems (bank, ATM, vehicle) cleanly and modularly.

***

### Method Overloading, Static vs Instance

#### Overloading

- Multiple methods with same name but different parameter lists.

```java
public int add(int a, int b) { return a+b; }
public float add(float a, float b) { return a+b; }
```


#### Static vs Instance

| Feature | Static | Instance |
| :-- | :-- | :-- |
| Memory | Class-level | Object-level |
| Access | ClassName.method() | obj.method() |
| Example | `Math.max(2,3);` | `acc.deposit(500);` |

**Exam Insight:**
Static methods don’t access instance variables.

***

### Encapsulation, Inheritance, Polymorphism, Abstraction

#### 1. Encapsulation

- Bundling data (fields) + methods into a single unit (class).
- Restricts direct access; use **getters/setters**.

**Analogy:** ATM gives access to your balance, but you can't directly access the cash box.

```java
public class Student {
    private int marks;
    public int getMarks() { return marks; }
    public void setMarks(int m) { marks = m; }
}
```


#### 2. Inheritance

- Classes can acquire properties from other classes.
- Enables code reuse and hierarchy.

```java
class Vehicle {
    int speed;
}
class Car extends Vehicle {
    int wheels = 4;
}
```


#### 3. Polymorphism

- Many forms: Method overriding, overloading.
- **Run-time polymorphism:** Calls to overridden methods via parent reference.

```java
class Vehicle {
    void run() { System.out.println("Vehicle Running"); }
}
class Bike extends Vehicle {
    void run() { System.out.println("Bike Running"); }
}

// Vehicle v = new Bike(); v.run(); // Output: Bike Running
```


#### 4. Abstraction

- Hiding details, showing only essential features (e.g., ATM interface—user sees buttons, not hardware inside).

**Key Takeaways/Revision Table**


| Concept | Real-World Analogy | Code Mechanism |
| :-- | :-- | :-- |
| Encapsulation | ATM, Bank locker | Private fields |
| Inheritance | Family tree | extends keyword |
| Polymorphism | Universal remote | method overriding |
| Abstraction | Car interface | abstract class/method |


***

### Garbage Collection

- Automatic memory management (frees unused objects).
- Relieves programmers from manual memory handling, reducing bugs.


#### ASCII Flowchart: Garbage Collection

```
[Object Created] -> [No references] -> [Eligible for GC] -> [GC removes]
```


#### Why Needed?

Prevents memory leaks, improves system performance and stability, essential for ATM/banking server reliability.

***

## Inheritance, Interfaces, Packages, Enumerations, Autoboxing, Metadata

### Single/Multilevel Inheritance, Method Overriding

- **Single:** One parent, one child.
- **Multilevel:** Parent → child → grandchild.

```java
class Account { ... }
class SavingsAccount extends Account { ... }
class SeniorCitizenAccount extends SavingsAccount { ... }
```

- **Method Overriding:** Child class redefines parent’s method.


### Abstract Classes, Interfaces, Package Creation

#### Abstract Classes

- Can have abstract (unimplemented) and concrete methods.
- **Can’t be instantiated.**

```java
abstract class Loan {
    abstract void approve();
    void process() { ... }
}
```


#### Interfaces

- 100% abstract; only method signatures (until Java 8).
- Supports multiple inheritance.

```java
interface ATMService {
    void withdraw();
}
```

- **Why both?**
Use abstract class when partial implementation is needed; interface for capability.


#### Package Creation

```java
package com.bank; // top of file

public class BankAccount { ... }
```

- Use `import` to use packages.

***

### java.lang, java.util, Wrapper Classes

- **java.lang:** Fundamental classes (String, System, Math)
- **java.util:** Utility (collections, Date, Scanner)
- **Wrapper Classes:** Convert primitives to objects (Integer, Double, etc.)

```java
int n = 5; // primitive
Integer nObj = Integer.valueOf(n); // wrapper
```


***

### Autoboxing/Unboxing, Enums, Metadata

- **Autoboxing:** Automatic conversion from primitive → wrapper.
- **Unboxing:** Wrapper → primitive.

```java
Integer age = 18;   // autoboxing
int realAge = age;  // unboxing
```

- **Enum:** List of constants.

```java
enum AccountType { SAVINGS, CURRENT, FIXED }
AccountType type = AccountType.SAVINGS;
```


***

## Exception Handling, Threading, Networking, JDBC

### Types of Exceptions, try-catch-finally, throw/throws, Custom Exceptions

- **Exception:** Problem at runtime.
- **try-catch-finally:** Handles exceptions gracefully.

```java
try {
    int a = 10 / 0;
} catch(ArithmeticException e) {
    System.out.println("Error: " + e.getMessage());
} finally {
    System.out.println("Cleanup, always runs!");
}
```

- **throw:** Manually throws an exception.
- **throws:** Declares an exception.
- **Custom exception:** Extends Exception class.

```java
class LowBalanceException extends Exception { ... }
```

**Exam Tip:**
Always write specific catch blocks, never catch Exception generally.

***

### Thread Class, Runnable Interface, Synchronization

#### Threading

Allows multiple tasks (threads) to execute concurrently (e.g., multiple ATM users).

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running!");
    }
}
MyThread t = new MyThread();
t.start();
```

- **Runnable Interface:** For classes that can't extend Thread.

```java
class BankingTask implements Runnable {
    public void run() { ... }
}
Thread t = new Thread(new BankingTask());
t.start();
```


#### Synchronization

Prevents conflicts (e.g., two users withdrawing from same account simultaneously).

```java
synchronized void withdraw(int amount) { ... }
```


***

### Networking Basics, TCP/UDP Concepts

- **Networking:** Connecting programs over networks.
- **TCP:** Reliable, connection-oriented (e.g., online banking)
- **UDP:** Fast, connectionless (e.g., live video streaming)

***

### JDBC Connectivity Steps with Real Database Example

#### Steps

1. Load Driver
2. Connect to DB
3. Create Statement
4. Execute Query
5. Process Results
6. Close Connection

#### Code Example

```java
import java.sql.*;
public class ATMDatabase {
    public static void main(String[] args) throws Exception {
        // 1. Load Driver
        Class.forName("com.mysql.cj.jdbc.Driver");
        // 2. Connect
        Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/bank", "root", "password");
        // 3. Create Statement
        Statement st = con.createStatement();
        // 4. Execute Query
        ResultSet rs = st.executeQuery("SELECT * FROM Account");
        // 5. Process Result
        while(rs.next()){
            System.out.println(rs.getInt("balance"));
        }
        // 6. Close
        con.close();
    }
}
```


#### ASCII Diagram: JDBC Workflow

```
[Java Application]--(JDBC Driver)->[Database]
        |
   [SQL Query]
        |
   [ResultSet]
```


***

## Applets and Event Handling

### Applet Lifecycle, GUI design using AWT

#### Applet: Small web-based Java program.

- **Lifecycle Stages:** init(), start(), paint(), stop(), destroy()

```java
import java.applet.*;
import java.awt.*;

public class MyApplet extends Applet {
    public void paint(Graphics g) {
        g.drawString("Welcome to Bank", 20, 20);
    }
}
```


#### GUI Design using AWT (Abstract Window Toolkit):

```java
import java.awt.*;
public class Form extends Frame {
    Form() {
        setTitle("ATM Form");
        setSize(300,150);
        setVisible(true);
    }
}
```


***

### Event Listener Model

#### Events: User actions (button click, mouse movement)

#### Listener: Responds to events

```java
import java.awt.event.*;
Button b = new Button("Withdraw");
b.addActionListener(new ActionListener(){
    public void actionPerformed(ActionEvent e){
        System.out.println("Withdraw Clicked!");
    }
});
```


***

### Inner Classes and Adapter Classes

- **Inner Class:** Class within a class, often used for event handling.
- **Adapter Class:** Provides empty default implementations—override only what you need.

```java
// Adapter example (for MouseListener)
addMouseListener(new MouseAdapter() {
    public void mouseClicked(MouseEvent e) {
        System.out.println("Clicked!");
    }
});
```


***

## Quick Revision \& Exam Pointers

- **Java’s main power:** WORA via bytecode and JVM
- **Core OOP:** Encapsulation, Inheritance, Polymorphism, Abstraction
- **Exception handling:** try-catch-finally, custom exceptions
- **Threads:** Use when simultaneous tasks needed
- **Networking:** TCP = reliable, UDP = fast
- **Packages:** Organize/reuse code
- **JDBC:** Real-world DB connectivity
- **Applets/Event handling:** Foundation for GUI apps

***

**Exam \& Interview Insights:**

- Always remember real-world analogies like ATM/Bank for OOP and threading questions.
- Diagrams help you visualize lifecycles and workflows.
- Consistency in examples (e.g., BankAccount) makes complex concepts easy to recall.

***
**End of Notes — Best of Luck!**

<div align="center">⁂</div>

[^1]: https://www.geeksforgeeks.org/java/how-jvm-works-jvm-architecture/

[^2]: https://www.edureka.co/blog/java-architecture/

[^3]: https://www.geeksforgeeks.org/java/differences-jdk-jre-jvm/

[^4]: https://www.digitalocean.com/community/tutorials/difference-jdk-vs-jre-vs-jvm

[^5]: https://www.programiz.com/java-programming/jvm-jre-jdk

[^6]: https://www.ibm.com/think/topics/jvm-vs-jre-vs-jdk

[^7]: https://www.octalsoftware.com/blog/java-vs-c

[^8]: https://unstop.com/blog/difference-between-cpp-and-java

[^9]: https://www.geeksforgeeks.org/cpp-vs-java/

[^10]: https://en.wikipedia.org/wiki/Comparison_of_Java_and_C++

[^11]: https://www.interviewbit.com/blog/difference-between-cpp-and-java/

[^12]: https://dev.to/imkrunalkanojiya/java-compilation-from-source-code-to-bytecode-execution-12hp

[^13]: https://www.geeksforgeeks.org/java/compilation-execution-java-program/

[^14]: https://www.knowledgeboat.com/question/describe-the-java-compilation-process-with-a-suitable--28317189245178630

[^15]: https://www.geeksforgeeks.org/java/byte-code-in-java/

[^16]: https://en.wikipedia.org/wiki/Java_bytecode

[^17]: https://www.azul.com/blog/understanding-java-compilation-from-bytecodes-to-machine-code/

[^18]: https://unstop.com/blog/data-types-in-java

[^19]: https://www.geeksforgeeks.org/java/java-data-types/

[^20]: https://www.w3schools.com/java/java_data_types.asp

[^21]: https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html

[^22]: https://www.w3schools.com/java/java_data_types_non-prim.asp

[^23]: https://herovired.com/learning-hub/topics/data-types-in-java/

[^24]: https://byjus.com/gate/difference-between-one-dimensional-and-two-dimensional-array/

[^25]: https://prepinsta.com/java/arrays/

[^26]: https://www.scholarhat.com/tutorial/java/java-arrays-single-and-multidimensional-aray

[^27]: https://www.geeksforgeeks.org/dsa/difference-between-one-dimensional-and-two-dimensional-array/

[^28]: https://www.w3schools.com/java/java_arrays_multi.asp

[^29]: https://www.geeksforgeeks.org/java/array-declarations-java-single-multidimensional/

[^30]: https://www.linkedin.com/pulse/introduction-arrays-java-understanding-one-dimensional

[^31]: https://www.geeksforgeeks.org/java/string-vs-stringbuilder-vs-stringbuffer-in-java/

[^32]: https://stackoverflow.com/questions/2971315/string-stringbuffer-and-stringbuilder

[^33]: https://www.geeksforgeeks.org/java/stringbuffer-vs-stringbuilder/

[^34]: https://www.shiksha.com/online-courses/articles/stringbuilder-vs-string-buffer/

[^35]: https://outcomeschool.com/blog/string-vs-stringbuffer-vs-stringbuilder

[^36]: https://www.codingshuttle.com/blog/a-complete-guide-to-string-string-buffer-and-string-builder-in-java

