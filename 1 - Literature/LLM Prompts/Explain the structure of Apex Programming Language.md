Structure of Apex Programming Language

  

Apex is an object-oriented language similar to Java and follows a structured format with classes, methods, variables, and exception handling. Below is a detailed breakdown of Apex’s structure:

1. Apex Class Structure

  

Apex code is written inside classes. A class is a blueprint for objects and contains variables and methods.

  

Basic Structure of an Apex Class

public class MyClass {

    // Member Variables (Instance Variables)

    public String name;

    private Integer age;

  

    // Constructor

    public MyClass(String name, Integer age) {

        this.name = name;

        this.age = age;

    }

  

    // Method

    public void displayInfo() {

        System.debug('Name: ' + name + ', Age: ' + age);

    }

}

1. Variables and Data Types

  

Apex supports primitive data types, collections, and complex objects.

  

Primitive Data Types

|   |   |
|---|---|
|Data Type|Description|
|Integer|32-bit number (-2,147,483,648 to 2,147,483,647)|
|Long|64-bit number|
|Decimal|Floating-point number|
|Double|64-bit floating-point|
|Boolean|true or false|
|String|Sequence of characters|
|Date|Date without time|
|Datetime|Date with time|
|Time|Time without date|

Example: Variable Declaration

public class Example {

    public Integer count = 10;

    public String name = 'Salesforce';

    public Boolean isActive = true;

}

1. Collections (Lists, Sets, and Maps)

  

Apex supports collections for handling multiple values efficiently.

  

List (Ordered Collection, Allows Duplicates)

List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};

System.debug(names[0]); // Alice

Set (Unordered Collection, No Duplicates)

Set<Integer> numbers = new Set<Integer>{1, 2, 3, 4, 5};

System.debug(numbers.contains(3)); // true

Map (Key-Value Pairs, No Duplicate Keys)

Map<Integer, String> employeeMap = new Map<Integer, String>{

    101 => 'John',

    102 => 'Doe'

};

System.debug(employeeMap.get(101)); // John

1. Control Flow Statements

  

Apex supports standard control flow structures:

  

Conditional Statements (if-else)

Integer age = 25;

if (age >= 18) {

    System.debug('Adult');

} else {

    System.debug('Minor');

}

Looping Statements

  

For Loop

for (Integer i = 0; i < 5; i++) {

    System.debug(i);

}

For-Each Loop (for collections)

List<String> fruits = new List<String>{'Apple', 'Banana', 'Cherry'};

for (String fruit : fruits) {

    System.debug(fruit);

}

While Loop

Integer i = 0;

while (i < 3) {

    System.debug(i);

    i++;

}

1. Methods in Apex

  

Methods define reusable blocks of code.

  

Method Syntax

public class MyClass {

    // Method with return type

    public String sayHello(String name) {

        return 'Hello, ' + name;

    }

}

Calling a Method

MyClass obj = new MyClass();

System.debug(obj.sayHello('Salesforce')); // Output: Hello, Salesforce

1. Exception Handling

  

Apex provides structured exception handling using try-catch-finally.

  

Example: Handling Exceptions

try {

    Integer result = 5 / 0; // Causes exception

} catch (Exception e) {

    System.debug('Error: ' + e.getMessage());

} finally {

    System.debug('Execution Completed');

}

1. Object-Oriented Features

  

Apex supports OOP principles like Encapsulation, Inheritance, and Polymorphism.

  

Encapsulation (Using Private Variables & Getters/Setters)

public class Person {

    private String name;

  

    public void setName(String newName) {

        name = newName;

    }

  

    public String getName() {

        return name;

    }

}

Inheritance (Using extends)

public class Animal {

    public void makeSound() {

        System.debug('Animal makes a sound');

    }

}

  

public class Dog extends Animal {

    public void makeSound() {

        System.debug('Dog barks');

    }

}

Polymorphism (Method Overriding)

public class Parent {

    public void showMessage() {

        System.debug('Parent Class');

    }

}

  

public class Child extends Parent {

    public void showMessage() {

        System.debug('Child Class');

    }

}

1. Apex Triggers (Automation on Database Events)

  

Apex triggers are used to execute logic when records are inserted, updated, or deleted.

  

Example: Before Insert Trigger

trigger AccountTrigger on Account (before insert) {

    for (Account acc : Trigger.new) {

        acc.Name = acc.Name + ' - Verified';

    }

}

1. Asynchronous Apex (Background Processing)

  

Apex supports asynchronous execution to handle long-running operations.

  

Future Method Example

public class AsyncExample {

    @future

    public static void processInBackground() {

        System.debug('Executed in Future Context');

    }

}

1. SOQL & DML (Salesforce Database Operations)

  

Apex interacts with Salesforce databases using SOQL (Salesforce Object Query Language) and DML (Data Manipulation Language).

  

SOQL Query Example

List<Account> accs = [SELECT Id, Name FROM Account WHERE Industry = 'Technology'];

DML Insert Example

Account acc = new Account(Name = 'New Company');

insert acc;

Summary

• Apex follows an object-oriented structure (Classes, Methods, Variables).

• It supports data handling using Collections (Lists, Sets, Maps).

• Control structures like if-else, loops, and exception handling are supported.

• Apex supports OOP principles like Encapsulation, Inheritance, and Polymorphism.

• Triggers, Asynchronous processing, and SOQL are used for Salesforce automation.

  

Would you like a more advanced example or a specific explanation?