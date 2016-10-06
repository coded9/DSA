#Naive approach
```
package sorting;

import java.io.BufferedReader;
import java.io.InputStreamReader;

public class SelectionSort {

	public static void main(String[] args) throws Exception{
		// TODO Auto-generated method stub
      BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
      String inp[];
      System.out.println("Give the input in a line");
      inp = br.readLine().split(" ");
      int[] arr = new int[inp.length];
      int i,j,min,k=0,temp;
      for(i=0;i<arr.length;i++){
    	  arr[i] = Integer.parseInt(inp[i]);
      }
      for(i=0;i<arr.length;i++){
    	  min = arr[i];
    	  for(j=i+1;j<arr.length;j++){
    		  if(arr[j]<min){
    			  min = arr[j];
    			  k = j;
    		  }
    	  }
    	  if(min<arr[i]){
    	  temp = arr[k];
    	  arr[k] = arr[i];
    	  arr[i] = temp;
    	  }
      }
      System.out.println("Array sorted using selection sort");
      for(i=0;i<arr.length;i++){
    	  System.out.print(arr[i]+" ");
      }
	}

}
```
#Optimized
```
package sorting;

import java.io.BufferedReader;
import java.io.InputStreamReader;

public class SelectionSort {

	public static void main(String[] args) throws Exception{
		// TODO Auto-generated method stub
      BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
      String inp[];
      System.out.println("Give the input in a line");
      inp = br.readLine().split(" ");
      int[] arr = new int[inp.length];
      int i,j,min,temp;
      for(i=0;i<arr.length;i++){
    	  arr[i] = Integer.parseInt(inp[i]);
      }
      for(i=0;i<arr.length;i++){
    	  min = i;
    	  for(j=i+1;j<arr.length;j++){
    		  if(arr[j]<arr[min]){
    			  min = j;
    		  }
    	  }
    	  
    	  temp = arr[min];
    	  arr[min] = arr[i];
    	  arr[i] = temp;
    	 
      }
      System.out.println("Array sorted using selection sort");
      for(i=0;i<arr.length;i++){
    	  System.out.print(arr[i]+" ");
      }
	}

}
```
