```
package linkedlists;

public class LinkedList {
     class Node{
	   int data;
	   Node next;
	   Node(int data){
		   this.data = data;
		   this.next = null;
	   }
   }
      Node head;
    void printList(){
    	 System.out.println("LinkedList  has been created");
	   Node current = head;
	   while(current!=null){
		   System.out.print(current.data+" ");
		   current = current.next;
	   }
	   System.out.println();
   }
    int listLength(){
	   Node current = head;
	   int len = 0;
	   while(current!=null){
		   len++;
		   current = current.next;
	   }
	   return len;
   }
    void insertAtHead(int data){
	   Node temp = new Node(data);
	   temp.next = head;
	   head = temp;
   }
    void insertAfter(int data,int position){
    	Node temp = new Node(data);
    	if(head==null){
    		head = temp;
    		return;
    	}
    	if(position==0){
    		temp.next = head;
    		head = temp;
    	}
    	else{
    		Node current = head;
    		while(position!=0&&current!=null){
    			current = current.next;
    			position--;
    		}
    		temp.next = current.next;
    		current.next = temp;
    	}
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
	   
   }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
     LinkedList llist = new LinkedList(); 
      llist.insertAtHead(5);
      llist.insertAtHead(2);
      llist.insertAfter(4,0);
      llist.insertAfter(6,2);
      llist.insertAfter(7,2);
      llist.insertAtTail(8);
      llist.insertAtTail(9);
      llist.printList();
	}

}
```
