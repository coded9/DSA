```java
package linkedlists;

import java.util.HashSet;

import linkedlists.LinkedList.Node;

public class LoopDetect {
    boolean detect(LinkedList ll){
    	 HashSet<Node> set= new HashSet<>();
    	 Node temp = ll.head;
    	 boolean flag = true;
    	 if(temp==null||temp.next==null){
    		 return false;
    	 }else{
    		 while(temp!=null){
    			 if(set.contains(temp)) return true;
    			 else set.add(temp);
    			 temp = temp.next;
    		 }
    		 return false;
    	 }
    	 
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
     LoopDetect ld = new LoopDetect();
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
