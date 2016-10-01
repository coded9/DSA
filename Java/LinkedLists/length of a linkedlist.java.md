````java
/*package linkedlists;

import linkedlists.LinkedList.Node;

public class LinkedLength {   
	int listLength(Node head){   //Recursive
		   if(head==null) return 0;
		   else return 1+listLength(head.next);
	   }
	int listLength(){ //Iterative
		
		Node current = head;
		 int len = 0;
		   while(current!=null){
			   len++;
			   current = current.next;
		   }
		   return len;
	}
}*/
package linkedlists;

import linkedlists.LinkedList.Node;

public class LinkedLength {
	 Node head;   
	int listLength(Node head){   //Recursive
		   if(head==null) return 0;
		   else return 1+listLength(head.next);
	   }
	int listLength(LinkedList llt){ //Iterative
		
		Node current = llt.head;
		 int len = 0;
		   while(current!=null){
			   len++;
			   current = current.next;
		   }
		   return len;
	}
	public static void main(String[] args){
		LinkedLength llen = new LinkedLength();
		LinkedList llt = new LinkedList();
		llt.insertAtHead(4);
		llt.insertAtHead(3);
		llt.insertAfter(5,1);
		llt.printList();
		llt.deleteHead();
		System.out.println(llen.listLength(llt.head));
		System.out.println(llen.listLength(llt));
	}
}

```
