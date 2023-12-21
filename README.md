Count the distinct elements in C++
Program to count the distinct elements  in C++, In this Program we will find out the elements which are unique in the array. 

Given an integer array, we have to print all the distinct element of the input array. input array may contain duplicate elements, we have to print the count of elements that are distinct.

Program to Counting distinct elements in an array in cpp
While loop in C
Methods Discussed in this Page are :
Method 1 : Using Two loops
Method 2 : Using hash Map
Let’s discuss each method one by one,

Method 1 :
In this method we will count the frequency of each elements using two for loops.

To check the status of visited elements create a array of size n and a variable say count_dis=0, to count the distinct element.
Run a loop from index 0 to n and check if (visited[i]==1) then skip that element.
Run a loop from index i+1 to n
Check if(arr[i]==arr[j]), then set visited[j]=1.
After complete iteration of inner for loop  increment the count_dis by 1.
At last, print the value of count_dis.
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(n)
Related Pages
Sorting elements of an array by frequency

Finding the Longest Palindrome in an Array

Finding  Repeating elements in an Array

Finding Non Repeating elements in an Array

Removing Duplicate elements from an array

Method 1 : Code in C++
Run
#include <bits/stdc++.h>
using namespace std;

// Main function to run the program
int main() 
{ 
    int arr[] = {10, 30, 10, 20, 40, 20, 50, 10}; 
    int n = sizeof(arr)/sizeof(arr[0]); 

    int visited[n], count_dis=0;

    for(int i=0; i<n; i++){

        if(visited[i]!=1){
           for(int j=i+1; j<n; j++){
              if(arr[i]==arr[j]){
                 visited[j]=1;
              }
            }
             count_dis++;
         }
     }
    cout<<count_dis;
    return 0; 
}
Output :
5
Method 2 :
In this method we will use hash-map to store the frequency of the elements.

Create an unordered_map say mp and a variable say count_dis=0 to count the unique elements.
Run a loop to iterate over array
Set mp[arr[i]]++
After, complete iteration,print the size of map, mp.size().
Method 2 : Code in C++
Run
#include <bits/stdc++.h>
using namespace std;

// Main function to run the program
int main() 
{ 
   int arr[] = {10, 30, 40, 20, 10, 20, 50, 10}; 
   int n = sizeof(arr)/sizeof(arr[0]); 

   unordered_map <int, int>mp;
   int count_dis=0;

   for(int i=0; i<n; i++)
      mp[arr[i]]++;

   cout<<mp.size();
}
Output :
5
