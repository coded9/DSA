#Naive approach
```java
package linkedlists;

import linkedlists.CircularLinkedList.Node;

public class SplitCircular {
   void split(CircularLinkedList cl){
	   Node temphead=null,temp=null;
	   int i,len,f1,f2;
	   i=0;len=cl.length();
	   CircularLinkedList cl1 = new CircularLinkedList();
	   CircularLinkedList cl2 = new CircularLinkedList();
	   temphead = cl.head;
	   if(len%2!=0) {f1=len/2 +1;f2=len/2;}
	   else f1=f2 = len/2;
	   while(i++<f1){
		   cl1.insertAtEnd(temphead.data);
		   temphead = temphead.next;
	   }
	   i=0;
	   while(i++<f2){
		   cl2.insertAtEnd(temphead.data);
		   temphead = temphead.next;
	   }
	   System.out.println("First Circular List");
	   cl1.printList();
	   System.out.println("Second");
	   cl2.printList();
	   
   }
	public static void main(String[] args) {
	 SplitCircular sc = new SplitCircular();
	 CircularLinkedList cl = new CircularLinkedList();
     cl.insertAtFront(2);
     cl.insertAtFront(3);
     cl.insertAtFront(4);
     cl.insertAtFront(5);
     cl.insertAtEnd(6);
     cl.printList();
     //System.out.println(cl.length());
     sc.split(cl);
	}

}

```
#Optimized
```java
package linkedlists;

import linkedlists.CircularLinkedList.Node;

public class SplitCircular1 {
    void split(CircularLinkedList cl){
    	Node head,head1=null,head2=null,slowp,fastp;
    	head = cl.head;
    	if(head==null) return;
    	slowp = head;
    	fastp = head;
    	while(fastp.next!=head&&fastp.next.next!=head){
    		fastp = fastp.next.next;
    		slowp = slowp.next;
    	}
    	if(fastp.next.next==head){
    		fastp = fastp.next;
    	}
    	head1 = head;
    	if(head.next!=head) head2 = slowp.next;//If there is only one node for splitting
    	fastp.next = slowp.next;
    	slowp.next = head;
    	System.out.println("First half");
    	printList(head1);
    	System.out.println("Second half");
    	printList(head2);
    }
    static void printList(Node head){
    	if(head==null) return;
    	Node temp = head;
    	System.out.print(head.data+" ");
        temp = temp.next;
    	while(temp!=head){
    		System.out.print(temp.data+" ");
    		temp = temp.next;
    	}
    	System.out.println();
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		 SplitCircular1 sc = new SplitCircular1();
		 CircularLinkedList cl = new CircularLinkedList();
	     cl.insertAtFront(2);
	     cl.insertAtFront(3);
	     cl.insertAtFront(4);
	     cl.insertAtFront(5);
	     cl.insertAtEnd(6);
	    cl.printList();
	     sc.split(cl);
	}

}

```
