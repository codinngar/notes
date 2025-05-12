## Access Modifiers
- `default`: visible to all classes in the same package
- `public`: visible in all classes in all packages in the same project
- `private`: visible only in the same class
- `protected`: visible to all classes in the same package or classes in other packages that are a subclass

## Static Keyword
- when using static with class attributes and methods it means that attribute or method belongs to this class and shared as the same between all objects and you can access it from objects but it's not recommended and it's not the best practice 

## Final Keyword
- when used with a variable it means this variable's value cannot be changed
- when used with a class it means that class cannot be subclassed (inherited)

## Abstract
- abstract classes cannot be instantiated but they can have a subclass
- abstract methods are declared without implementation and the subclasses of the abstract class must implement the abstract methods

## Method Chaining
```java
// Box.java
public class Box {  
    private int width;
    private int height;
  
    public Box setWidth(int width) {
        this.width = width;
        return this;
    }

    public Box setHeight(int height) {
        this.height = height;
        return this;
    }
}

// Main.java
Box box = new Box().setWidth(10).setHeight(2);
```

## Enum
```java
// Switch.java
public enum Switch {
    ADD, DELETE;
    
    public int getValue() {
        return switch (this) {
            case ADD -> 1;
            case DELETE -> 2;
        };
    }
}

// Main.java
Swith.ADD.getValue(); // 1
Swith.DELETE.getValue(); // 2
```

## Static and Dynamic Binding
- static binding happens in overloading
- dynamic binding happens in overriding

## Record
- you can override record constructor and methods
- record attributes must be final
```java
import java.util.Objects;

// normal java clasws
public class Person {
    private final String name;
    private final int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    @Override
    public String toString() {
        // body
    }

    @Override
    public int hashCode() {
        // body
    }
	
    @Override
    public int equals(final object obj) {
        // body
    }
}

// the record class is alternative to the above code
pubic record Person(String name, int age) {
	// body
}
```

## Instance Initializer Block
- runs each time you instantiate an object
- can be used to initialize non-static variables

## Static Initializer Block
- runs once when the class is initialized
- can be used to initialize static variables

## Interface
- interface cannot be instantiated
- interface is an alternative to abstract class with abstract methods
- all methods in interface is `public abstract` by default so you are able to not write it
- variables is final and static so you must initialize them inside the interface
```java
interface Person {
	int age = 24;
	void greet();
}

class Man implements Person {
	@Override
	public void greet() {
		// body
	}
}
```

## Thread
- make thread by extending `Thread`
```java
class MyThread extends Thread {
	@Override
	public void run() {
		// body
	}
}

MyThread myThread = new MyThread();
myThread.start();
```

- make thread by implementing `Runnable` interface
```java
class MyRunnable implements Runnable {
	@Override
	public void run() {
		// body
	}
}

MyRunnable myRunnable = new MyRunnable();
Thread thread = new Thread(myRunnable);
thread.start();
```

## Generics
```java
// general type
class Print<T> {}

// type must be Animal or a class extends Animal
// use extends even if it is an interface
// when using multible types classes must be before interfaces
class Print<T extends Animal & Flying> {}

// wild card is used when data type is unknown
public void print(List<?> list) {}
```

## Exceptions
```java
try { // code that my throw an exception
	int x = 8 / 0;
	System.out.println(x);
} catch (ArithmeticException e) { // what to do if there is an exception
	System.out.println("Division by zero");
} finally { // this code block always execute
	System.out.println("Always execute");
}
```