```java
package linkedlists;
import linkedlists.LinkedList.Node;
public class Reverse {
	 Node head ;
	void reverse(){  //Iterative
		  
		Node current = head,next=null,prev=null;
		   while(current!=null){
			   next = current.next;
			   current.next = prev;
			   prev = current;
			   current = next;
		   }
		   head = prev;
	   }
	Node reverse(Node current,Node prev){ //Recursive
		if(current.next==null){
			head = current;
			current.next = prev;
			return null;
		}
		Node next = current.next;
		current.next = prev;
		reverse(next,current);
		return head;
	}
	

}

```
