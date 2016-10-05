#Naive Approach
```java
package linkedlists;

import linkedlists.CircularLinkedList.Node;

public class SortedInsertCircular {
    void sortedInsert(CircularLinkedList cl,int data){
    	Node temp,head,prev=null,new_node;
    	temp = cl.head;
    	head = cl.head;
    	if(temp==null) {
    		cl.insertAtEnd(data);
    		cl.printList();
    		return;
    	}
    	if(temp.data>=data){
    		cl.insertAtFront(data);
    		cl.printList();
    		return;
    	}
        new_node = cl.new Node(data);
    	while(temp.data<=data&&temp.next!=head){
    		prev = temp;
    		temp = temp.next;
    	}
    	
     if(temp.next!=head||temp.data>=data){
    	 prev.next = new_node;
    	 new_node.next = temp;
     }else if(temp.data<=data){
    	 temp.next = new_node;
	     new_node.next = head;
     }
    	cl.printList();
    	return;
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
      SortedInsertCircular sic =  new SortedInsertCircular();
      CircularLinkedList cl = new CircularLinkedList();
      cl.insertAtEnd(2);
      cl.insertAtEnd(5);
      cl.insertAtEnd(8);
      cl.insertAtEnd(10);
      cl.printList();
      sic.sortedInsert(cl,11);
      sic.sortedInsert(cl, 1);
	}

}

```
#Optimized
```
package linkedlists;

import linkedlists.CircularLinkedList.Node;

public class SortedInsertCircular {
    void sortedInsert(CircularLinkedList cl,int data){
    	Node temp,head,prev=null,new_node;
    	temp = cl.head;
    	head = cl.head;
    	new_node = cl.new Node(data);
    	if(temp==null) {
    		temp=new_node;
    		head = temp;
    		cl.printList();
    		return;
    	}
    	if(temp.data>=data){
    		while(temp.next!=head){
    			temp = temp.next;
    		}
    		temp.next = new_node;	
    		new_node.next = head;
    		cl.head = new_node;
    		cl.printList();
    		return;
    	}
        
    	while(temp.data<=data&&temp.next!=head){
    		temp = temp.next;
    	}
    	
    	 new_node.next = temp.next;
    	 temp.next = new_node;
    	 cl.printList();
    	 return;
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
      SortedInsertCircular sic =  new SortedInsertCircular();
      CircularLinkedList cl = new CircularLinkedList();
      cl.insertAtEnd(2);
      cl.insertAtEnd(5);
      cl.insertAtEnd(8);
      cl.insertAtEnd(10);
      cl.printList();
      sic.sortedInsert(cl,11);
      sic.sortedInsert(cl, 1);
	}

}
```
