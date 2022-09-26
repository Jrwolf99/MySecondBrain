---
tags:
- programming
---
# Binary Search

Binary Search is an algorithm (see [[algorithms]]) that is used to search a sorted array by **repeatedly dividing the search intervals in half**. This means that it should reduce the time to O(Log n).


#### the algorithm
-   Begin with the mid element of the whole array as a search key.
-   If the value of the search key is equal to the item then return an index of the search key.
-   Or if the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half.
-   Otherwise, narrow it to the upper half.
-   Repeatedly check from the second point until the value is found or the interval is empty.

#### code example

```java
  
  //where l is left index, r is right index, and x is number we are searching for in arr.
  //start with l being 0 and r being n-1.
  
  int binarySearch(int arr[], int l, int r, int x)
    {
        if (r >= l) {
            int mid = l + (r - l) / 2;
 
            // If the element is present at the
            // middle itself
            if (arr[mid] == x)
                return mid;
 
            // If element is smaller than mid, then
            // it can only be present in left subarray
            if (arr[mid] > x)
                return binarySearch(arr, l, mid - 1, x);
 
            // Else the element can only be present
            // in right subarray
            return binarySearch(arr, mid + 1, r, x);
        }
 
        // We reach here when element is not present
        // in array
        return -1;
    }
```



#### resources
https://www.geeksforgeeks.org/binary-search/