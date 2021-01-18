# C-Internship-Paper-4
## Table of contents
*Question 1
*Question 2
*Question 3

##Question 1
<p>
Q1. Two elements whose sum is closest to zero.
An Array of integers is given, both +ve and -ve. You need to find the two elements such that their sum is closest to zero. For the below array, the program should print -80 and 85.
  </p>
## code:
<b> Sort the array and for every element add it with previous element and compare it to previous sum </b>

```c++
#include<bits/stdc++.h>
using namespace std;
int main(){
   int n; //array elements
   cin>>n;
   int arr[n];
   for(int i=0;i<n;i++){
      cin>>arr[i];
   }
   sort(arr,arr+n);
   int minimum=INT_MAX,first,second;
   int i=1;
   while(i<n){
        int now_sum=abs(arr[i]+arr[i-1]);
        if(now_sum<=minimum){
             minimum=now_sum;
             first=i-1;second=i;
         }
        i++;
   }
   cout<<arr[first]<<" "<<arr[second]<<" "<<"are two numbers";
   return 0;
   }
   ```
 ## Question 2:
 Q2. Find duplicates in O(n) time and O(1) extra space.

Given an array of n elements that contains elements from 0 to n-1, with any of these numbers appearing any number of times. Find these repeating numbers in O(n) and using only constant memory space.

Input : n = 7 and array[] = {1, 2, 3, 6, 3, 6, 1} 
Output: 1, 3, 6 
Explanation: The numbers 1 , 3 and 6 appear more than once in the array. 

Input : n = 5 and array[] = {1, 2, 3, 4 ,3} 
Output: 3 
Explanation: The number 3 appears more than once in the array.


##Code
```c++
#include <bits/stdc++.h>
using namespace std;
int main(){
   int n;
   cin>>n;
   int arr[n];
   for(int i=0;i<n;i++)cin>>arr[i];
   for(int i=0;i<n;i++){  //treaverse array
       if (arr[abs(arr[i])] >= 0) //if  arr[abs(array[i])] element is positive it is not duplicate
            arr[abs(arr[i])] = -arr[abs(arr[i])];
        else
            cout<<abs(arr[i])<< " ";  //else it is duplicate so print it
    }
    return 0;
} 
```
 ## Question 3:
 <p>
 Q3. Find the minimum distance between two numbers.

Given an unsorted array arr[] and two numbers x and y, find the minimum distance between x and y in arr[]. The array might also contain duplicates. You may assume that both x and y are different and present in arr[].

Input: arr[] = {1, 2}, x = 1, y = 2 
Output: Minimum distance between 1 and 2 is 1. 
Explanation: 1 is at index 0 and 2 is at index 1, so the distance is 1 

Input: arr[] = {3, 4, 5}, x = 3, y = 5 
Output: Minimum distance between 3 and 5 is 2. 
Explanation:3 is at index 0 and 5 is at index 2, so the distance is 2 

Input: arr[] = {3, 5, 4, 2, 6, 5, 6, 6, 5, 4, 8, 3}, x = 3, y = 6 
Output: Minimum distance between 3 and 6 is 4. 
Explanation:3 is at index 0 and 6 is at index 5, so the distance is 4 

Input: arr[] = {2, 5, 3, 5, 4, 4, 2, 3}, x = 3, y = 2 
Output: Minimum distance between 3 and 2 is 1. 
Explanation:3 is at index 7 and 2 is at index 6, so the distance is 1
</p>

## Approach:
Using two loops ,
the outer loop runs from start to end , the inner loop runs from start+1 to end 
If x and y are found store the minimum distance .
Time  complexity: O(n^2)
## code:

```c++
#include <bits/stdc++.h> 
using namespace std;  
int main()  
{ 
    int n;
    cin>>n;
    int arr[n]; 
    int x,y;
    cin>>x>>y;
    int minimum= INT_MAX; 
    for (int i = 0; i < n; i++) { 
        for (int j = i+1; j < n; j++) { 
            if( (x == arr[i] && y == arr[j] || y == arr[i] && x == arr[j]) && minimum > abs(i-j))  minimum= abs(i-j);
        } 
    } 
    return minimum; 
} 
```
