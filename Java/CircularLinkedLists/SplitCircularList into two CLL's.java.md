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
