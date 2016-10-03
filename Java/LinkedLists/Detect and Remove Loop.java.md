```java
package linkedlists;

import linkedlists.LinkedList.Node;

public class RemoveLoop {
    void detectAndRemoveLoop(LinkedList ll){
    Node slow = ll.head;
    if(slow==null||slow.next==null) return;
    Node fast = ll.head;
    while(fast!=null&&fast.next!=null){
    	slow=slow.next;
    	fast = fast.next.next;
    	if(slow==fast) break;
    	
    }
 if(fast==null||fast.next==null){
	 System.out.println("No loop in the list");
	 return;
 }else{
	 System.out.println("Loop is found at Node "+slow.data);
    Node prev=null;
    Node temp = ll.head;
    if(temp!=slow){
    	prev = slow;
    	slow = slow.next;
    	temp = temp.next;
    }
    prev.next = null;
    }
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
    RemoveLoop rl = new RemoveLoop();
    LinkedList ll = new LinkedList();
    ll.insertAtHead(2);
    ll.insertAtHead(3);
    ll.insertAtHead(4);
    ll.insertAtHead(5);
    ll.insertAtHead(6);
    ll.printList();
  //  ll.head.next.next.next.next = ll.head.next;
    rl.detectAndRemoveLoop(ll);
    ll.printList();
	}

}

```
