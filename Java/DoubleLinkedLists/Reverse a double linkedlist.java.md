#Naive approach
```
package linkedlists;

import linkedlists.DoubleLinkedList.Node;

public class ReverseDouble {
    void reverse(DoubleLinkedList dll){
    	Node curr,next,prev;
    	curr = dll.head;
    	while(curr.next!=null){
    		next = curr.next;
    		curr.next = curr.prev;
    		curr.prev = next;
    		curr = next;
    		
    	}
    	
    	curr.next = curr.prev;
    	curr.prev = null;
    	
    	dll.head = curr;
    	dll.printList();
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
    ReverseDouble rd = new ReverseDouble();
    DoubleLinkedList dll =  new DoubleLinkedList();
    dll.insertAtHead(2);
    dll.insertAtHead(3);
    dll.insertAtHead(4);
    dll.insertAtHead(5);
    dll.insertAtHead(6);
    dll.insertAtTail(1);
    dll.printList();
    rd.reverse(dll);
	}

}

```
