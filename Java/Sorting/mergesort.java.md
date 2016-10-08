```java
package sorting;

import java.io.BufferedReader;
import java.io.InputStreamReader;

public class MergeSort {
    void mergeSort(int[] arr,int l,int r){
    	if(l<r){
    	int m = (l+r)/2;
    	mergeSort(arr,l,m);
    	mergeSort(arr,m+1,r);
    	merge(arr,l,m,r);
    	}
    	
    }
    void merge(int[] arr,int l,int m,int r){
    	int n1 = m-l+1,n2 = r-m,i,j,k;
    	int[] L = new int[n1];
    	int[] R = new int[n2];
    	for(i=0;i<n1;i++){
    		L[i] = arr[l+i];
    	}
    	for(j=0;j<n2;j++){
    		R[j] = arr[m+1+j];
    	}
    	k = l;
    	i=0;j=0;
    	while(i<n1&&j<n2){
    		if(L[i]<=R[j]){
    			arr[k] = L[i];
    			i++;
    		}
    		else{
    			arr[k] = R[j];
    			j++;
    		}
    		k++;
    	}
    	while(i<n1){
    		arr[k] = L[i];
    		i++;k++;
    	}
    	while(j<n2){
    		arr[k] = R[j];
    		j++;k++;
    	}
    }
	public static void main(String[] args) throws Exception{
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
	      String inp[];
	      System.out.println("Give the input in a line");
	      inp = br.readLine().split(" ");
	      int[] arr = new int[inp.length];
	      int i,j;
	      for(i=0;i<arr.length;i++){
	    	  arr[i] = Integer.parseInt(inp[i]);
	      }
	      new MergeSort().mergeSort(arr,0,arr.length-1);
	      System.out.println("Array sorted using merge sort");
	      for(i=0;i<arr.length;i++){
	    	  System.out.print(arr[i]+" ");
	      }
	}

}

```
