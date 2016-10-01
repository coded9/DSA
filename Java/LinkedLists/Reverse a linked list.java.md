```java
/*package linkedlists;
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
	

}*/
package linkedlists;
import linkedlists.LinkedList.Node;
public class Reverse {
	
	 void reverse(LinkedList ll){  //Iterative
		  
		
		Node current = ll.head,next=null,prev=null;
		   while(current!=null){
			   next = current.next;
			   current.next = prev;
			   prev = current;
			   current = next;
		   }
		   ll.head = prev;
	   }
	 Node reverse(Node current,Node prev,LinkedList ll){ //Recursive
			if(current.next==null){
				ll.head = current;
				current.next = prev;
				return null;
			}
			Node next = current.next;
			current.next = prev;
			reverse(next,current,ll);
			return ll.head;
		}
	 void reverseRecur(LinkedList ll){
	ll.head = reverse(ll.head,null,ll);
	 }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		LinkedList ll = new LinkedList();
		ll.insertAtHead(2);
	      ll.insertAtHead(3);
	      ll.insertAtHead(4);
	      ll.insertAtHead(5);
	      ll.printList();
	      Reverse r = new Reverse();
	      r.reverseRecur(ll);
	      ll.printList();
	}

}


```
