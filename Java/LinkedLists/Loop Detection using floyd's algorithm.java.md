```java
package linkedlists;

import linkedlists.LinkedList.Node;

public class LoopDetect1 {
    boolean detect(LinkedList ll){
    	Node slow = ll.head;
    	if(slow==null|slow.next==null) return false;
    	Node fast = slow.next;
    	while(slow!=null&&fast!=null&&fast.next!=null){
    		slow = slow.next;
    		fast = fast.next.next;
    		if(slow==fast) return true;
    	}
    	return false;
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		LoopDetect1 ld = new LoopDetect1();
	     LinkedList ll = new LinkedList();
	     ll.insertAtHead(2);
	     ll.insertAtHead(3);
	     ll.insertAtHead(5);
	     ll.insertAtHead(6);
	     ll.head.next.next = ll.head.next;
	    System.out.println(ld.detect(ll)?"Loop detected":"No loop");
	}

}

```
