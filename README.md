# 193454-cat_2

public class Linked_List {


    private static class Node {
        int data;
        Node next;

      
        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    
    private Node head;

 
    public Linked_List() {
        head = null;
    }

 
    public void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        newNode.next = head; 
        head = newNode;      
    }

    
    public void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
          
            head = newNode;
        } else {
           
            Node current = head;
            while (current.next != null) {
                current = current.next;
            }
          
            current.next = newNode;
        }
    }

   
    public void deleteFromBeginning() {
        if (head == null) {
            System.out.println("List is empty. Nothing to delete.");
        } else {
            // Move 'head' to the next node, effectively removing the first node.
            head = head.next;
        }
    }

    
    public void printList() {
        Node current = head;
        while (current != null) {
            System.out.print(current.data + " -> ");
            current = current.next;
        }
        System.out.println("null");
    }

   
    public static void main(String[] args) {
        Linked_List list = new Linked_List();

       
        list.insertAtBeginning(10);
        list.insertAtBeginning(20);

       
        list.insertAtEnd(30);

      
        System.out.println("Linked List after insertions:");
        list.printList(); // Expected: 20 -> 10 -> 30 -> null

      
        list.deleteFromBeginning();
        System.out.println("Linked List after deletion from beginning:");
        list.printList(); // Expected: 10 -> 30 -> null
    }
}
