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