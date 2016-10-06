#Iterative
```
package linkedlists;

import linkedlists.LinkedList.Node;

public class SortedMerge1 {
    Node sortMerge(Node a,Node b){
    	if(a==null) return b;
    	if(b==null) return a;
    	Node head = null;
    	if(a.data<b.data){
    		head = a;
    	}else{
    		head = b;
    		b = a;
    		a = head;
    	}
    	while(a.next!=null){
    		if (a.next.data > b.data) {
    		      Node tmp = a.next;
    		      a.next = b;
    		      b = tmp;
    		    }
    		    a = a.next;
    		  } 
    		  if (a.next == null) a.next = b;
    	
    return head;
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
     SortedMerge1 sm = new SortedMerge1();
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
#Recursive
```
package linkedlists;

import linkedlists.LinkedList.Node;

public class SortedMerge3 {
   Node sortMerge(Node a,Node b){
	   Node head = null;
	   if(a==null) return b;
	   else if(b==null) return a;
	   if(a.data<=b.data){
		   a.next = sortMerge(a.next,b);
		   return a;
	   }
	   else{
		b.next = sortMerge(a,b.next);
		return b;
	   }
   }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		SortedMerge3 sm = new SortedMerge3();
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
