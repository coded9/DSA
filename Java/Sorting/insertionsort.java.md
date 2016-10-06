
```java
package sorting;

import java.io.BufferedReader;
import java.io.InputStreamReader;

public class InsertionSort {

	public static void main(String[] args) throws Exception{
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
	      String inp[];
	      System.out.println("Give the input in a line");
	      inp = br.readLine().split(" ");
	      int[] arr = new int[inp.length];
	      int i,j,hole,val;
	      for(i=0;i<arr.length;i++){
	    	  arr[i] = Integer.parseInt(inp[i]);
	      }
	      for(i=1;i<arr.length;i++){
	    	  hole = i;
	    	  val = arr[i];
	    	  while(hole>0&&arr[hole-1]>val){
	    		  arr[hole] = arr[hole-1];
	    		  hole--;
	    	  }
	    	  arr[hole] = val;
	      }
	      System.out.println("Array sorted using insertion sort");
	      for(i=0;i<arr.length;i++){
	    	  System.out.print(arr[i]+" ");
	      }
	      
	}

}

```
