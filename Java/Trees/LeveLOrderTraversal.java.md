```java
package trees;

import java.util.LinkedList;
import java.util.Queue;

public class LeveLOrder {
	
	static void levelOrder(Node root){
		if(root==null) return;
		Queue<Node> nodelist = new LinkedList();
		nodelist.add(root);
	    while(!nodelist.isEmpty()){
		    Node current = nodelist.poll();
		    System.out.print(current.data+" ");
			if(current.left!=null) nodelist.add(current.left);
			if(current.right!=null) nodelist.add(current.right);
			
		}
	}

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		 BinaryTree tree = new BinaryTree();
	      tree.root = new Node(1);
	      tree.root.left = new Node(2);
	      tree.root.right = new Node(3);
	      tree.root.left.left = new Node(4);
	      tree.root.left.right = new Node(5);
	      tree.root.right.left = new Node(6);
	      tree.root.right.right = new Node(7);
	      levelOrder(tree.root);
	}

}


```
        
	
	
