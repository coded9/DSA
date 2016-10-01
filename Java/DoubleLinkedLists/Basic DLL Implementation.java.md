```
package linkedlists;

public class DoubleLinkedList {
    class Node{
    	int data;
    	Node prev,next;
    	Node(int data){
    		this.data = data;
    		this.prev = null;
    		this.next = null;
    	}
    }
     static Node head;
    void insertAtHead(int data){
    	Node temp = new Node(data);
    	if(head==null){
    		head = temp;
    		return;
    	}
    	temp.next = head;
    	head.prev = temp;
    	head = temp;
    	
    }
    void insertAtTail(int data){
    	Node temp = new Node(data);
    	if(head==null){
    		head = temp;
    		return;
    	}
    	Node current = head;
    	while(current.next!=null){
    		current = current.next;	
    	}
    	current.next = temp;
    	temp.prev = current;
    }
    void insertAfter(int position,int data){
    	if(head==null){
    		return;
    	}
    	Node temp = new Node(data);
    	Node current = head;
    	while(position!=0&&current!=null){
    		current = current.next;
    		position--;
    	}
    	if(current==null){
    		System.out.println("Cannot insert at given position");
    		return;
    	}
    	temp.next = current.next;
    	temp.prev = current;
    	current.next = temp;
    }
    void insertBefore(int position,int data){
    	if(position==0){
    		insertAtHead(data);
    		return;
    	}
    	Node current = head;
    	Node temp = new Node(data);
    	while(position!=0&&current!=null){
    		//System.out.println(current.data);
    		current = current.next;
    		position--;
    	}
    	if(current==null){
    		System.out.println("Cannot insert at given position");
    		return;
    	}
    	//System.out.println(current.prev.data+" "+temp.data);
    	current.prev.next = temp;
    	temp.prev = current.prev;
    	temp.next = current;
    	current.prev = temp;
    	//printList();
    //	System.out.println(current.prev.next.data);
    	
    	
    }
    void deleteHead(){
    	if(head==null){
    		System.out.println("Cannot delete:DLL is empty");
    		return;
    	}
    	head = head.next;
    	head.prev = null;
    }
    void deleteTail(){
    	if(head==null){
    		System.out.println("Cannot delete:DLL is empty");
    		return;
    	}
    	if(head.next==null){
    		head = null;
    		return;
    	}
    	Node temp = head;
    	while(temp.next!=null){
    		temp = temp.next;
    	}
    	temp.prev.next = null;
    }
    void deleteNode(Node del){
    	if(head==null||del==null) return;
    	if(head==del){
    		head = del.next;
    		return;
    	}
    	Node temp = head;
    	while(temp!=del){
    		temp = temp.next;
    	}
    	if(temp.next==null){
    		temp.prev.next = null;
    		return;
    	}
    	temp.prev.next = temp.next;
    	temp.next.prev = temp.prev;
    }
    void printList(){
    	if(head==null){
    		System.out.println("Cannot print:DLL is empty");
    		return;
    	}
    	Node temp = head;
    	System.out.println("Printing DLL");
    	while(temp!=null){
    	System.out.print(temp.data+" ");
    	temp = temp.next;
    	}
    	System.out.println();
    }
    
	public static void main(String[] args) {
		DoubleLinkedList dll = new DoubleLinkedList();
		dll.insertAtHead(1);
		dll.insertAtHead(2);
		dll.insertAtTail(5);
		dll.insertAtTail(7);
		dll.insertAtHead(4);
        dll.printList();
        dll.deleteHead();
        dll.printList();
        dll.deleteHead();
        dll.printList();
        dll.deleteTail();
        dll.printList();
        dll.insertAfter(1, 25);
        dll.insertAfter(2, 18);
        dll.insertAfter(3, 19);
        dll.deleteNode(head.next.next.next.next);
        dll.printList();
        dll.insertBefore(3, 20);
        dll.printList();
        dll.insertBefore(4, 22);
        dll.insertBefore(3, 23);
        dll.insertAfter(0, 16);
        dll.insertAfter(3, 34);
        dll.insertAfter(5, 29);
        dll.printList();
        
	}

}

```
