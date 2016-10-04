```java
package linkedlists;



import linkedlists.LinkedList.Node;

public class ReverseGroup {
	
   Node reverseGroup(Node head,int k){
	   Node curr=null,next=null,prev=null;
	   int i=0;
	   
	   curr = head;
	   while(i<k&&curr!=null){
		   next = curr.next;
		   curr.next = prev;
		   prev = curr;
		   curr = next;
		   i++;
	   }
	   if(next!=null){
		  head.next = reverseGroup(next,k);
	   }
	   return prev;
   }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
      ReverseGroup rg = new ReverseGroup();
      LinkedList ll = new LinkedList();
      ll.insertAtHead(7);
      ll.insertAtHead(6);
      ll.insertAtHead(5);
      ll.insertAtHead(4);
      ll.insertAtHead(3);
      ll.insertAtHead(2);
      ll.insertAtHead(1);
      ll.printList();
     ll.head = rg.reverseGroup(ll.head,2);
     ll.printList();
     
	}

}

```
