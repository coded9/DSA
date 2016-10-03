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
#Optimized
```java
package linkedlists;

import linkedlists.LinkedList.Node;

public class AddLinkedLists1 {
    Node addLists(Node first,Node second){
    	LinkedList hm = new LinkedList();
    	Node dummy = hm.new Node(0),curr;
    	int sum=0,carry=0;
    	curr = dummy;
    	while(first!=null||second!=null){
    		sum = carry+(first!=null?first.data:0)
    				+(second!=null?second.data:0);
    	     carry = sum/10;
    		curr.next = hm.new Node(sum%10);
    		curr = curr.next;
    		if(first!=null) first = first.next;
    		if(second!=null) second = second.next;
    	}
    	if(carry>0) curr.next = hm.new Node(carry);
    	return dummy.next;
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
     rs.head = al.addLists(ll.head,ll2.head);
     rs.printList();
	}

}
```
# Using Stacks
```java
package linkedlists;

import java.util.Stack;

import linkedlists.LinkedList.Node;

public class AddLinkedLists2 {
    Node addLists(Node first,Node second){
		Stack<Integer> st1 = new Stack<>();
		Stack<Integer> st2 = new Stack<>();
		LinkedList hm = new LinkedList();
		Node head=null,temp;
		while(first!=null){
			st1.push(first.data);
			first = first.next;
		}
		while(second!=null){
			st2.push(second.data);
			second = second.next;
		}
		int sum,carry=0;
		//System.out.println(st1+" "+st2);
        while(!st1.isEmpty()||!st2.isEmpty()) {
        	sum = carry;
        	if(!st1.isEmpty()) sum+=st1.pop();
        	if(!st2.isEmpty()) sum += st2.pop();
        	carry = sum/10;
        	hm.insertAtHead(sum%10);
        }
    	if(carry>0) hm.insertAtHead(carry);
    	return hm.head;
    }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
    AddLinkedLists2 al = new AddLinkedLists2();
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
    rs.head = al.addLists(ll.head,ll2.head);
    rs.printList();
	}

}

```
