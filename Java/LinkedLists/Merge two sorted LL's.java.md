#Method1 (dummy node)
```java
package linkedlists;

import linkedlists.LinkedList.Node;

public class SortedMerge {
    Node sortMerge(Node a,Node b){
    	Node dummy = new LinkedList().new Node(-1);
    	Node curr = dummy;
    	dummy.next =  null;
    		while(true){
    			if(a==null&&b==null){
    				break;
    	    	}
    	    	else if(a==null){
    	    		curr.next = b;
    	    		break;
    	    	}
    	    	else if(b==null){
    	    		curr.next = a;
    	    		break;
    	    	}
    			if(a.data<=b.data){
    				curr.next = a;
    				a = a.next;
    			}
    			else{
    				curr.next = b;
    				b = b.next;
    			}
    			curr = curr.next;
    		}
    	
    return dummy.next;
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
     SortedMerge sm = new SortedMerge();
     LinkedList l1 = new LinkedList();
     LinkedList l2 = new LinkedList();
     LinkedList res = new LinkedList();
     l1.insertAtHead(11);
     /*l1.insertAtHead(8);
     l1.insertAtHead(4);*/
     l1.insertAtHead(1);
     l1.printList();
     l2.insertAtHead(9);
     l2.insertAtHead(3);
     l2.insertAtHead(0);
     l2.printList();
     res.head = sm.sortMerge(l1.head, l2.head);
     res.printList();
	}

}


```
#Method 2(Iterative)
```java
package linkedlists;

import linkedlists.LinkedList.Node;

public class SortedMerge2 {
	Node sortMerge(Node a, Node b) {
		if (a == null && b == null) {
			return null;
		} else if (a == null)
			return b;
		else if (b == null)
			return a;
		else {
			Node head = null;
			Node prev = null;
			while (a != null && b != null) {
				if (head == null) {
					if (a.data <= b.data) {
						head = a;
						prev = a;
						a = a.next;
					} else {
						head = b;
						prev = b;
						b = b.next;
					}
				} else
				{
					if (a.data <= b.data) {
					   prev.next = a;
						a = a.next;
					} else {
						prev.next = b;
						b = b.next; 
					}
					prev = prev.next;
			}
		}
			if (a == null)
				prev.next = b;

			if (b == null)
				prev.next = a;

			return head; 
		}
	}

	public static void main(String[] args) {
		// TODO auto-generated method stub
		SortedMerge2 sm = new SortedMerge2();
		LinkedList l1 = new LinkedList();
		LinkedList l2 = new LinkedList();
		LinkedList res = new LinkedList();
		l1.insertAtHead(11);
		l1.insertAtHead(8);
		l1.insertAtHead(4);
		l1.insertAtHead(1);
		l1.printList();
		l2.insertAtHead(9);
		l2.insertAtHead(3);
		l2.insertAtHead(0);
		l2.printList();
		res.head = sm.sortMerge(l1.head, l2.head);
		res.printList();
	}

}

```
