

---

### **1. What are the main features of Java?**
Java is a popular programming language known for the following features:
- **Platform Independent** (Write Once, Run Anywhere)
- **Object-Oriented** (Follows OOP principles)
- **Robust and Secure** (Strong memory management and security features)
- **Multithreading** (Supports concurrent execution)
- **Garbage Collection** (Automatic memory management)

Example:
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

---

### **2. What is the difference between JDK, JRE, and JVM?**
- **JVM (Java Virtual Machine)**: Runs Java bytecode on different platforms.
- **JRE (Java Runtime Environment)**: Includes JVM and libraries for running Java applications.
- **JDK (Java Development Kit)**: Includes JRE + development tools like compiler (`javac`).

---

### **3. Explain the concept of Object-Oriented Programming (OOP) in Java.**
OOP principles:
- **Encapsulation**: Hiding data using access modifiers.
- **Inheritance**: Reusing code from parent classes.
- **Polymorphism**: Many forms (method overloading and overriding).
- **Abstraction**: Hiding implementation details.

Example:
```java
// Parent class
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

// Child class
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.makeSound();  // Output: Dog barks
    }
}
```

---

### **7. What is method overloading and method overriding?**
- **Method Overloading**: Same method name, different parameters (Compile-time polymorphism).
- **Method Overriding**: Subclass provides a new implementation of a method from the parent class (Runtime polymorphism).

Example:
```java
class MathOperations {
    // Overloading
    int add(int a, int b) {
        return a + b;
    }
    int add(int a, int b, int c) {
        return a + b + c;
    }
}

class Parent {
    void show() {
        System.out.println("Parent class");
    }
}

class Child extends Parent {
    // Overriding
    @Override
    void show() {
        System.out.println("Child class");
    }
}

public class OverloadingOverridingExample {
    public static void main(String[] args) {
        MathOperations obj = new MathOperations();
        System.out.println(obj.add(2, 3));  // 5
        System.out.println(obj.add(2, 3, 4));  // 9

        Parent obj2 = new Child();
        obj2.show();  // Output: Child class
    }
}
```

---

### **12. What is the difference between an interface and an abstract class?**
| Feature          | Interface | Abstract Class |
|-----------------|-----------|---------------|
| Methods         | Only abstract methods (before Java 8) | Can have both abstract and concrete methods |
| Fields         | Public, static, and final only | Can have instance variables |
| Multiple Inheritance | Supported | Not supported |

Example:
```java
interface Vehicle {
    void start();
}

abstract class Car {
    abstract void accelerate();
    void brake() {
        System.out.println("Car is stopping");
    }
}

class Tesla extends Car implements Vehicle {
    public void start() {
        System.out.println("Tesla starts");
    }

    public void accelerate() {
        System.out.println("Tesla accelerates");
    }
}

public class InterfaceAbstractExample {
    public static void main(String[] args) {
        Tesla myTesla = new Tesla();
        myTesla.start();
        myTesla.accelerate();
        myTesla.brake();
    }
}
```

---

### **20. What is the difference between `ArrayList` and `LinkedList`?**
- **`ArrayList`**: Uses dynamic array, fast for search operations.
- **`LinkedList`**: Uses doubly linked list, fast for insert/delete operations.

Example:
```java
import java.util.*;

public class ListExample {
    public static void main(String[] args) {
        List<String> arrayList = new ArrayList<>();
        arrayList.add("Apple");
        arrayList.add("Banana");

        List<String> linkedList = new LinkedList<>();
        linkedList.add("Carrot");
        linkedList.add("Dates");

        System.out.println(arrayList.get(1));  // Output: Banana
        System.out.println(linkedList.get(1)); // Output: Dates
    }
}
```

---

### **25. What is multithreading in Java?**
Multithreading allows multiple threads to run concurrently.

Example:
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running: " + Thread.currentThread().getName());
    }
}

public class ThreadExample {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start();
    }
}
```

---

### **34. What is a lambda expression in Java?**
Lambda expressions provide a concise way to write anonymous functions.

Example:
```java
interface Greeting {
    void sayHello();
}

public class LambdaExample {
    public static void main(String[] args) {
        Greeting greeting = () -> System.out.println("Hello from Lambda!");
        greeting.sayHello();
    }
}
```

---

### **36. What is the difference between `Comparator` and `Comparable`?**
- **`Comparable`**: Used for natural ordering (implements `compareTo()`).
- **`Comparator`**: Used for custom sorting (implements `compare()`).

Example:
```java
import java.util.*;

class Student implements Comparable<Student> {
    String name;
    int age;
    
    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public int compareTo(Student other) {
        return Integer.compare(this.age, other.age);
    }
}

public class ComparableExample {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();
        students.add(new Student("Alice", 25));
        students.add(new Student("Bob", 22));
        
        Collections.sort(students);
        
        for (Student s : students) {
            System.out.println(s.name + " - " + s.age);
        }
    }
}
```

---
🚀
