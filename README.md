# LinkedList-
LinkedList implementation using Stack
// Node class for Linked List
class Node {
    int data;
    Node next;

    // Constructor
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

// Stack using Linked List
class StackLinkedList {
    private Node top; // Top of the stack

    // Constructor
    StackLinkedList() {
        this.top = null;
    }

    // Push operation (Insert at head)
    public void push(int data) {
        Node newNode = new Node(data);
        newNode.next = top; // Link new node to the previous top
        top = newNode; // Update top to new node
        System.out.println("Pushed: " + data);
    }

    // Pop operation (Remove from head)
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack Underflow! Stack is empty.");
            return -1;
        }
        int poppedData = top.data;
        top = top.next; // Move top to the next node
        System.out.println("Popped: " + poppedData);
        return poppedData;
    }

    // Peek operation (Return top element without removal)
    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty.");
            return -1;
        }
        return top.data;
    }

    // Check if stack is empty
    public boolean isEmpty() {
        return top == null;
    }

    // Display stack elements
    public void display() {
        if (isEmpty()) {
            System.out.println("Stack is empty.");
            return;
        }
        System.out.print("Stack Elements: ");
        Node temp = top;
        while (temp != null) {
            System.out.print(temp.data + " -> ");
            temp = temp.next;
        }
        System.out.println("NULL");
    }
}

// Main Class
public class LinkedListStack {
    public static void main(String[] args) {
        StackLinkedList stack = new StackLinkedList();

        stack.push(10);
        stack.push(20);
        stack.push(30);

        stack.display();

        System.out.println("Top element is: " + stack.peek());

        stack.pop();
        stack.display();

        stack.pop();
        stack.pop();
        stack.pop(); // Attempt to pop from empty stack
    }
}
