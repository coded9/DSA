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
    	if(head==null){
    		System.out.println("LinkedList is Empty:Cannot Print");
    		return;
    	}
    	 System.out.println("Printing LinkedList");
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
    		if(current==null){
    			System.out.println("Cannot insert at given position");
    			return;
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
   void deleteNodeWithKey(int data){
	   Node temp = head,prev = null;
	   if(temp!=null&&temp.data == data){
			 head = temp.next;
			 return;
		}
	   while(temp!=null&&temp.data!=data){
		  prev = temp;
		  temp = temp.next;
	   }
	   if(temp==null) {
		   System.out.println("Cannot delete:Node doesn't exist");
		   return;
	   }
	   prev.next = temp.next;
   }
   void deleteNodeAtPos(int position){
	   Node temp,prev;
	   if(head==null){
		   System.out.println("LinkedList is empty:Cannot delete");
		   return;
	   }
	   else if(position==0){
		   temp = head.next;
		   head = temp;
		   return;
	   }
	   else{
		   temp = head;prev = null;
		   while(position!=0&&temp!=null){
			   prev = temp;
			   temp = temp.next;
			   position--;
		   }
		   if(temp==null){
			   System.out.println("Cannot delete node at given position");
			   return;
		   }
		   prev.next = temp.next;
	   }
   }
   void deleteHead(){
	   if(head==null){
		   System.out.println("LinkedList is empty:Cannot delete");
		   return;
	   }
	   Node temp;
	   temp = head.next;
	   head = temp;
   }
   void deleteTail(){
	   if(head==null) {
		   System.out.println("LinkedList is empty:Cannot delete");
		   return;
	   }
	   if(head.next==null){
		   head = null;
		   return;
	   }
	   Node temp = head,prev = null;
	   while(temp.next!=null){
		   prev = temp;
		   temp = temp.next;
	   }
	   prev.next = null;
   }
   void deleteAll(){
	   head = null;
   }
   void getPosition(int data){
	   if(head==null){
		   System.out.println("LinkedList is Empty");
		   return;
	   }
	   Node temp = head;
	   int pos = 0;
	   while(temp!=null&&temp.data!=data){
		   temp = temp.next;
		   pos++;
	   }
	   if(temp==null){
		   System.out.println("Node doesn't exist");
		   return;
	   }
	   System.out.println("Node is found at position "+ pos);
   }
   void reversePrint(){
	   
   }
	public static void main(String[] args) {
     LinkedList llist = new LinkedList(); 
      llist.insertAtHead(5);
      llist.insertAtHead(2);
      llist.insertAfter(4,0);
      llist.insertAfter(6,2);
      llist.insertAfter(7,2);
      llist.insertAtTail(8);
      llist.insertAtTail(9);
      llist.insertAtTail(12);
      llist.insertAtHead(13);
      llist.printList();
      llist.deleteNodeWithKey(14);
      llist.printList();
      llist.deleteHead();
      llist.printList();
      llist.deleteHead();
      llist.printList();
      llist.deleteHead();
      llist.printList();
      llist.deleteTail();
      llist.deleteNodeAtPos(3);
      llist.printList();
      llist.insertAfter(10,2);
      llist.insertAfter(11,3);
      llist.printList();
      llist.deleteNodeAtPos(3);
      llist.printList();
      llist.getPosition(12);
      //llist.deleteAll();
      //llist.printList();
	}

}

```
