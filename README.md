# Java-Code-for-finding-the-Smallest-Element-in-an-Array

We will discuss different methods to find the smallest element among the elements of the given array.

Methods Covered :
Method 1: Using Iteration
Method 2: Top-down Recursion.
Method 3: Bottom-up Approach
Method 1 :
Objective: Find the Smallest element in array Java

Declare a variable say min and initialize it with array first element.
Run a loop from index 1 to N, and check
If arr[i]<min, then set min = arr[i]
After complete iteration print min.
Java Program for finding the smallest number in an array
Run
import java.util.Scanner;

public class Main
{
  public static void main(String args[])
  {

     int arr[] = {12, 13, 1, 10, 34, 10};

     int min = arr[0];

     for(int i=0; i<arr.length; i++) { if(min > arr[i])
         {
            min = arr[i];
         }

     }

     System.out.print(min); 
  }
}
Output
1
Related Pages
Given a string s, remove all its adjacent duplicate characters recursively
 
Find Largest element in an array
 
Find the Smallest and largest element in an array

Find Second Smallest Element in an Array

Calculate the sum of elements in an array 

Method 2 (Using Recursion) :
Create a recursive function say getmin(int arr[], int n)
Base Condition : if(n==1) return arr[0]
Otherwise, return min(arr[n-1], getmin(arr, n-1))
Smallest Element
Method 2 : Java Code
Run
import java.util.Scanner;
import java.util.*;

public class Main
{ 
   static int getmin(int arr[], int n){
       if(n==1)
       return arr[0];

       return Math.min(arr[n-1], getmin(arr, n-1));
   }
   public static void main(String args[])
   {

      int arr[] = {12, 13, 1, 10, 34, 10};
      int n = arr.length;
      System.out.print(getmin(arr, n)); 
   }
}
Output
1
Method 3 (Using Bottom up recursion)
Call a function : minimum(int arr[], int i, int end)

With initial call up values as minimum(arr, 0, end)
Initially passing end as the index of last array element
Initially passing ‘i’ as 0
Recursively reach iteration where reading 2nd last element
Find smaller between 2nd last and last array elements
And return the result to min value of the previous recursive iteration
In each of the remaining recursive callups find the smaller b/w current array index element and current min value
Pass final min value from last recursive callup to main and print
Method 3 : Java Code
Run
import java.util.Scanner;
import java.util.*;

public class Main
{ 
   static int getmin(int arr[], int i, int end)
   {
      int min;

      if(i == end-1)
         return (arr[i] < arr[i + 1]) ? arr[i] : arr[i + 1];

      min = getmin(arr, i + 1, end);

      return (arr[i] < min) ? arr[i] : min;
   }

   public static void main(String args[])
   {

     int arr[] = {12, 13, 1, 10, 34, 10};
     int end = arr.length-1;
     System.out.print(getmin(arr, 0, end)); 
   }
}
Output
1
