```java
package linkedlists;

import linkedlists.LinkedList.Node;

public class AddLinkedLists1 {
    Node addLists(Node first,Node second,Node res){
    	Node prev=null,temp=null;
    	LinkedList hm = new LinkedList();
    	int sum=0,carry=0;
    	while(first!=null||second!=null){
    		sum = carry+(first!=null?first.data:0)
    				+(second!=null?second.data:0);
    		if(sum>=10) carry = 1;
    		else carry = 0;
    		sum = sum%10;
    		temp = hm.new Node(sum);
    		if(res==null){
    			res = temp;
    		}else{
    			prev.next = temp;
    		}
    		prev = temp;
    		if(first!=null) first = first.next;
    		if(second!=null) second = second.next;
    	}
    	if(carry>0) temp.next = hm.new Node(carry);
    	
    	return res;
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
     AddLinkedLists1 al = new AddLinkedLists1();
     LinkedList ll = new LinkedList();
     LinkedList ll2 = new LinkedList();
     LinkedList rs = new LinkedList();
     ll.insertAtHead(4);
     ll.insertAtHead(3);
     ll.insertAtHead(2);
     ll.insertAtHead(1);
     ll2.insertAtTail(9);
     ll2.insertAtTail(8);
     ll.printList();
     ll2.printList();
     rs.head = al.addLists(ll.head,ll2.head,rs.head);
     rs.printList();
	}

}

```
