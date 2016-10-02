```java
package linkedlists;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

import linkedlists.LinkedList.Node;
public class SwapNodes {
    void swap(LinkedList ll,int a,int b){
    	if(a==b) return;
    	Node currA,prevA=null,currB,prevB=null,temp;
    	currA = ll.head;
    	while(currA!=null&&currA.data!=a){
    		prevA = currA;
    		currA = currA.next;
    	}
    	currB = ll.head;
    	while(currB!=null&&currB.data!=b){
    		prevB = currB;
    		currB = currB.next;
    	}
    	if(currA==null||currB==null) return;
    	if(prevA!=null) prevA.next = currB; else ll.head = currB;
    	if(prevB!=null) prevB.next = currA; else ll.head = currA;
    	temp = currA.next;
    	currA.next = currB.next;
    	currB.next = temp;  	
    }
	public static void main(String[] args) throws IOException {
		// TODO Auto-generated method stub
	  String inp[];	
	  BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
      LinkedList ll = new LinkedList();
      ll.insertAtHead(2);
      ll.insertAtHead(3);
      ll.insertAtHead(4);
      ll.insertAtHead(5);
      ll.printList();
      SwapNodes sn = new SwapNodes();
      System.out.println("Enter the nodes you want to swap");
      inp = br.readLine().split(" ");
      int a = Integer.parseInt(inp[0]);
      int b = Integer.parseInt(inp[1]);
      sn.swap(ll,a,b);
      ll.printList();
	}

}

```
