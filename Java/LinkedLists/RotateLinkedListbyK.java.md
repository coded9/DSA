#Naive Approach
```java
package linkedlists;

import java.util.Scanner;

import linkedlists.LinkedList.Node;

public class RotateLinked {
   void rotate(LinkedList ll,int k){
	   Node temp=ll.head,temp2,prev=null;
	   if(temp==null) return;
	   k--;
	   while(temp!=null&&k>=0){
		   prev = temp;
		   temp = temp.next;
		   k--;
	   }
	   prev.next = null;
	   temp2 = ll.head;
	   ll.head = temp;
	   while(temp.next!=null){
		   temp = temp.next;
	   }
	   temp.next = temp2;
	   ll.printList();
   }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		RotateLinked rl = new RotateLinked();
       LinkedList ll = new LinkedList();
       ll.insertAtHead(6);
       ll.insertAtHead(5);
       ll.insertAtHead(4);
       ll.insertAtHead(3);
       ll.insertAtHead(2);
       ll.insertAtHead(1);
      // 1->2->3->4->5->6
       ll.printList();
       Scanner sc = new Scanner(System.in);
       int k = sc.nextInt();
       rl.rotate(ll,k);
	}

}

```
# Optimized
```
package linkedlists;

import java.util.Scanner;

import linkedlists.LinkedList.Node;

public class RotateLinked {
   void rotate(LinkedList ll,int k){
	   Node temp=ll.head,kthNode;
	   if(temp==null) return;
	   k--;
	   while(temp!=null&&k>0){
		   temp = temp.next;
		   k--;
	   }
	   if(temp==null) return;
	   kthNode= temp;
	   while(temp.next!=null){
		   temp = temp.next;
	   }
	   temp.next = ll.head;
	   ll.head = kthNode.next;
	   kthNode.next = null;
	   ll.printList();
   }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		RotateLinked rl = new RotateLinked();
       LinkedList ll = new LinkedList();
       ll.insertAtHead(6);
       ll.insertAtHead(5);
       ll.insertAtHead(4);
       ll.insertAtHead(3);
       ll.insertAtHead(2);
       ll.insertAtHead(1);
      // 1->2->3->4->5->6
       ll.printList();
       Scanner sc = new Scanner(System.in);
       int k = sc.nextInt();
       rl.rotate(ll,k);
	}

}
```
