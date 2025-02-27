
```java
class Stack {
    private int size;
    private int top;
    private int[] array;

    public Stack(int size) {
        this.size = size;
        this.top = 0;
        this.array = new int[size];
    }

    public void push(int data) {
        if (top == size) {
            System.out.println("Stack is full!");
            return;
        }
        array[top] = data;
        top++;
    }

    public void pop() {
        if (top == 0) {
            System.out.println("Stack is empty!");
            return;
        }
        top--;
    }

    public void peek() {
        for (int i = 0; i < top; i++) {
            System.out.println(array[i]);
        }
    }
}
```