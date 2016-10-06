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
    				Node new_node = new LinkedList().new Node(a.data);
    				curr.next = new_node;
    				a = a.next;
    			}
    			else{
    				Node new_node = new LinkedList().new Node(b.data);
    				curr.next = new_node;
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
