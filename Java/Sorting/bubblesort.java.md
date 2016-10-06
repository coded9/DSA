#Naive approach
```java
package sorting;

import java.io.BufferedReader;
import java.io.InputStreamReader;

public class BubbleSort {

	public static void main(String[] args) throws Exception{
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
	      String inp[];
	      System.out.println("Give the input in a line");
	      inp = br.readLine().split(" ");
	      int[] arr = new int[inp.length];
	      int i,j,temp;
	      for(i=0;i<arr.length;i++){
	    	  arr[i] = Integer.parseInt(inp[i]);
	      }
	      for(i=0;i<arr.length;i++){
	    	  for(j=0;j<arr.length-1;j++){
	    		  if(arr[j]>arr[j+1]){
	    			  temp = arr[j];
	    			  arr[j] = arr[j+1];
	    			  arr[j+1] = temp;
	    		  }
	    	  }
	      }
	      System.out.println("Array sorted using bubble sort");
	      for(i=0;i<arr.length;i++){
	    	  System.out.print(arr[i]+" ");
	      }
	}

}

```
