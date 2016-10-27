
```
package com.stacks;

import java.util.NoSuchElementException;

public class Stack {
    int arr[];
    int capacity,top,len;
	public Stack(int n){
		capacity = n;
		arr = new int[n];
		top = -1;
		len = 0;
	}
	void push(int data) throws Exception{
		if(isFull()){
			throw new IndexOutOfBoundsException("Stack Overflow");
		}
		arr[++top] = data;
		//System.out.println(arr[0]);
		len++;
	}
	int pop(){
		if(isEmpty()){
			throw new NoSuchElementException("Stack Underflow ");
		}
		len--;
		return arr[top--];
	}
	int peek(){
		if(isEmpty()){
			throw new NoSuchElementException("Stack Underflow ");
		}
		return arr[top];
	}
	boolean isFull(){
		return top==capacity-1;
	}
	boolean isEmpty(){
		return top==-1;
	}
	int size(){
		return len;
	}
	void print(){
		if(len==0) System.out.println("Stack is Empty");
		else{
		StringBuilder sb = new StringBuilder();
		for(int i=0;i<=top;i++){
			sb.append(arr[i]+" ");
		}
		System.out.println(sb);
		}
	}
	
	public static void main(String[] args) {
		// TODO Auto-generated method stub
     Stack st = new Stack(10);
     try{
     st.push(10);
     st.push(20);
     st.push(30);
     st.push(40);
     st.push(50);
     st.push(60);
     st.push(70);
     st.push(80);
     st.push(90);
     st.push(100);
     System.out.println(st.size());
     st.print();
     System.out.println(st.peek());
     st.pop();
     st.print();
     System.out.println(st.peek());
     st.pop();
     st.print();
     System.out.println(st.size());
     }catch(Exception e){
    	 System.out.println(e.getMessage());
     }
	}

}
```
