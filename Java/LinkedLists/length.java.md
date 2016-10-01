package linkedlists;

import linkedlists.LinkedList.Node;

public class LinkedLength {
	 Node head;   
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
}
