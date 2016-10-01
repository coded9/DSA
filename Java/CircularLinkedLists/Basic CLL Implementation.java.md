
```java
package linkedlists;

public class CircularLinkedList {
    class Node{
    	int data;
    	Node next;
    	Node(int data){
    		this.data = data;
    		this.next = null;
    	}
    }
    int length(){
    	if(head==null) return 0;
    	Node temp = head.next;
    	int count = 0 ;
    	while(temp!=head&&temp!=null){
    		temp = temp.next;
    		count++;
    	}
    	return count+1;
    }
    void printList(){
    	if(head==null){ 
    		System.out.println("CLL is Empty");
    		return;
    	}
    	System.out.println("CLL is printing");
    	Node temp = head.next;
    	System.out.print(head.data+" ");
    	while(temp!=head){
    		System.out.print(temp.data+" ");
    		temp = temp.next;
    	}
    	System.out.println();
    }
    void insertAtPos(int position,int data){
    	
    }
    void insertAtFront(int data){
    	Node temp = new Node(data),last;
    	if(head==null){
    		head = temp;
    		head.next=head;
    		return;
    	}
    	temp.next = head;
    	if(head.next==head){
    		head.next = temp;
    		head = temp;
    	}
    	last = head.next;
    	while(last.next!=head){
    		last = last.next;
    	}
    	last.next = temp;
    	head = temp;
    }
    void insertAtEnd(int data){
    	Node temp = new Node(data),last;
    	if(head==null){
    		head = temp;
    		head.next = head;
    		return;
    	}
    	
    	if(head.next==head){
    		head.next = temp;
    		temp.next = head;
    		//System.out.println(head.data+" "+temp.data);
    		return;
    	}
    	last = head.next;
    	while(last!=head&&last.next!=head){
    		last = last.next;
    	}
    	last.next = temp;
    	temp.next = head;
    	
    }
    void deleteAtFront(){
    	if(head==null){
    		System.out.println("Cannot delete:List is Empty");
    		return;
    	}
    	if(head.next==head){
    		head = null;
    		return;
    	}
    	Node last = head.next;
    	while(last.next!=head){
    		last = last.next;
    	}
    	last.next = head.next;
    	head = head.next;
    }
    void deleteAtEnd(){
    	if(head==null){
    		System.out.println("Cannot delete:List is Empty");
    		return;
    	}
    	if(head.next==head){
    		head = null;
    		return;
    	}
    	Node last = head.next;
    	while(last.next.next!=head){
    		last =last.next;
    	}
    	last.next = head;
    }
    void deleteAtPos(int position){
    	
    }
    
    Node head;
	public static void main(String[] args) {
		// TODO Auto-generated method stub
      CircularLinkedList cll = new CircularLinkedList();
      cll.insertAtFront(3);
      cll.printList();
      System.out.println(cll.length());
      cll.insertAtEnd(5);
      //cll.printList();
      cll.insertAtEnd(6);
      //cll.printList();
      cll.insertAtFront(2);
      cll.insertAtFront(4);
      cll.insertAtFront(5);
      cll.insertAtEnd(7);
      cll.insertAtEnd(8);
     // cll.deleteAtFront();
      cll.printList();
      cll.deleteAtEnd();
      cll.printList();
      cll.deleteAtEnd();
      cll.deleteAtEnd();
      cll.deleteAtEnd();
      cll.deleteAtEnd();
      cll.deleteAtEnd();
      cll.deleteAtEnd();
      cll.deleteAtEnd();
      cll.deleteAtEnd();
      cll.printList();
	}

}

```
