## Encapsulation
Encapsulation bundles data (fields) and methods (functions) that operate on that data into a single unit (class), restricting direct access to some of an object’s components to ensure data integrity. It’s achieved using access modifiers (private, public, protected) and getter and setter methods.

```java
public class Person {
    private String name; // Private field

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String name) {
        this.name = name;
    }
}
```

## Inheritance
Inheritance allows a class (subclass) to inherit fields and methods from another class (superclass), promoting code reuse. In Java, it’s implemented using the extends keyword. Java supports single inheritance (a class can only extend one superclass).

```java
public class Animal {
    public void eat() {
        System.out.println("This animal eats food.");
    }
}

public class Dog extends Animal {
    public void bark() {
        System.out.println("The dog barks.");
    }
}

class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat(); // Inherited from Animal
        dog.bark(); // Defined in Dog
    }
}
```

## Polymorphism
Polymorphism allows objects to be treated as instances of their superclass, enabling methods to behave differently based on the object calling them. It’s achieved through method overriding (runtime polymorphism) and method overloading (compile-time polymorphism).
- **Method Overriding**: A subclass provides a specific implementation of a method defined in its superclass.
- **Method Overloading**: Multiple methods in the same class have the same name but different parameters.

```java
// Overriding
public class Animal {
    public void makeSound() {
        System.out.println("Some generic animal sound");
    }
}

public class Cat extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Meow");
    }
}

class Main {
    public static void main(String[] args) {
        Animal animal = new Cat(); // Polymorphic behavior
        animal.makeSound(); // Outputs: Meow
    }
}
```

```java
// Overloading
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }
}

class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.add(5, 3)); // Outputs: 8
        System.out.println(calc.add(5.5, 3.3)); // Outputs: 8.8
    }
}
```

## Abstraction
Abstraction hides complex implementation details and exposes only the necessary functionality. In Java, it’s achieved using abstract classes or interfaces.
- **Abstract Class**: A class that cannot be instantiated and may contain abstract methods (without implementation).
- **Interface**: A contract specifying methods that implementing classes must define (Java 8+ allows default and static methods in interfaces).

```java
// Abstract
public abstract class Shape {
    public abstract double calculateArea(); // Abstract method

    public void display() { // Concrete method
        System.out.println("This is a shape.");
    }
}

public class Circle extends Shape {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}
```

```java
// Interface
public interface Vehicle {
    void start();
    void stop();
}

public class Car implements Vehicle {
    @Override
    public void start() {
        System.out.println("Car started.");
    }

    @Override
    public void stop() {
        System.out.println("Car stopped.");
    }
}
```