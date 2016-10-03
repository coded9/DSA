#Naive Approach
```java
package linkedlists;

import linkedlists.LinkedList.Node;

public class AddLinkedLists {
    String toString(LinkedList A){
    	String s = "";
    	Node temp = A.head;
    	while(temp!=null){
    		s += ""+temp.data;
    		temp = temp.next;
    	}
    	return s;
    }
   void numtoLinked(int num){
    	LinkedList res = new LinkedList();
    	while(num!=0){
    		res.insertAtHead(num%10);
    		num = num/10;
    	}
    	res.reverse();
    	res.printList();
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
     AddLinkedLists al = new AddLinkedLists();
     LinkedList ll = new LinkedList();
    ll.insertAtHead(4);
     ll.insertAtHead(3);
     ll.insertAtHead(2);
     ll.printList();
     ll.reverse();
     
     int a=0,b=0;
     String str;
     str = al.toString(ll);
     if(str.length()>0){
    	 a = Integer.parseInt(str);
     }
     LinkedList ll2 = new LinkedList();
     ll2.insertAtHead(3);
     ll2.insertAtHead(5);
     ll2.printList();
     ll2.reverse();
     str = al.toString(ll2);
     if(str.length()>0) b = Integer.parseInt(str);
     al.numtoLinked(a+b);
     
	}
	

}

```
