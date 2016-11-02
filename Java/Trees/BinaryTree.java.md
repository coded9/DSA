```java
package trees;

public class BinaryTree {

	Node root;
	public BinaryTree(int key){
		root = new Node(key);
	}
	public BinaryTree(){
		root = null;
	}
	void printInOrder(Node node){
		if(node==null) return;
		 printInOrder(node.left);
        System.out.print(node.key+" ");
        printInOrder(node.right);
	}
	void printPreOrder(Node node){
		if(node==null) return;
		System.out.print(node.key+" ");
		printPreOrder(node.left);
		printPreOrder(node.right);
	}
	void printPostOrder(Node node){
		if(node==null) return;
		printPostOrder(node.left);
		printPostOrder(node.right);
		System.out.print(node.key+" ");
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
      System.out.println("### Inorder traversal ###");
      tree.printInOrder(tree.root);
      System.out.println("\n### Preorder traversal ###");
      tree.printPreOrder(tree.root);
      System.out.println("\n### Postorder traversal ###");
      tree.printPostOrder(tree.root);
	}

}


```
