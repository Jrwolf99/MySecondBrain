---
tags:
- programming
---
# Sliding Window

Sliding Window is a "technique" used to make [[algorithm]]s. This is common in solving leetcode style problem



## an example 
Find largest sum of 5 consecutive elements. 

```
[ 5, 7, 1, 4, 3, 6, 2, 9, 2 ]
```

#### **brute force**
this solution is in O(n)
```javascript
const getMaxSumOfFiveContiguousElements = (arr) => {
  let maxSum = -Infinity;
  let currSum;

  for (let i = 0; i <= arr.length - 5; i++) {
    currSum = 0;

    for (let j = i; j < i + 5; j++) {
      currSum += arr[j];
    }

    maxSum = Math.max(maxSum, currSum);
  }

  return maxSum;
};
```
![[Pasted image 20220926100552.png]]



#### **Is there a better way? SLIDING WINDOW!**
```
[ 5, 7, 1, 4, 3, 6, 2, 9, 2 ]
```

![[Pasted image 20220926100637.png]]
visualize this box as a "window".

if we are looking for the sum of 5 consecutive numbers, 5+*7+1+4+3* is **20**

the sum of the next iteration is *7+1+4+3*+6 = **21**.

All we really needed to do was 20 - 5 + 6, because the 5 left our "window" and the 6 entered our "window".

Here is the code for it:
```javascript
const getLargestSumOfFiveConsecutiveElements = (arr) => {
  let currSum = getSum(arr, 0, 4);
  let largestSum = currSum;

  for (let i = 1; i <= arr.length - 5; i++) {
    currSum -= arr[i - 1]; // subtract element to the left of curr window
    currSum += arr[i + 4]; // add last element in curr window
    largestSum = Math.max(largestSum, currSum);
  }

  return largestSum;
};

const getSum = (arr, start, end) => {
  let sum = 0;

  for (let i = start; i <= end; i++) {
    sum += arr[i];
  }

  return sum;
};
```




#### resources

Adam Zerner explains it really well [here](https://stackoverflow.com/questions/8269916/what-is-sliding-window-[[algorithm]]-examples)