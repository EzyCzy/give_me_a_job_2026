## Leetcode 33: Search in Rotated Sorted Array

### Solution:
Consider the usual setup for a binary search:
`lo = 0, hi = n -1, mid = lo + hi >> 1` If `arr[mid] = target`, we're done. Otherwise, notice that at least one half of the search space is sorted. That is either `lo...m-1` or `m+1...hi`, if not both. We can verify if a half is sorted if `arr[lo] < arr[m]` or `arr[m] < arr[hi]` respectively for the left and right halves. Pick one of the sorted half and check whether `target` can exist within it. If thats the case pick the half, otherwise the other half. 

### Exercise: 
Prove the implemented algorithm correctly reports whether `target` exist within `arr`.

### Time Complexity
The initial search space is length of arr, `n`. Since, we reduce the search space by half every iteration, worst case our search will be size of 1. We would then have $$\frac{n}{2^k}=1$$, where `k` is size of search space. So $$k=\log_2 n$$. Therefore, the time complexity is $$O(n\log n)$$
