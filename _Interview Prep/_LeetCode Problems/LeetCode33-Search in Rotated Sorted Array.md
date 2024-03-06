[Reference](https://leetcode.com/problems/search-in-rotated-sorted-array/description/) 

- **Input**: A rotated sorted array `nums` of distinct integers and a target value `target`.
- **Output**: The index of `target` in the array `nums`, or -1 if `target` is not in `nums`.
<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/search-in-rotated-sorted-array/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To efficiently solve this problem:

- Use binary search to find the pivot index, which is the index of the smallest element in the rotated sorted array.
- Once the pivot index is found, use binary search again to search for `target` in the appropriate half of the array.

Here's a high-level approach to solving Problem 33:

1. Use binary search to find the pivot index:
    - Initialize pointers `left` and `right` to the first and last indices of the array.
    - While `left < right`:
        - Calculate the middle index `mid`.
        - If `nums[mid] > nums[right]`, set `left = mid + 1`.
        - Otherwise, set `right = mid`.
    - After the loop, `left` will be the pivot index.
2. Use binary search to find `target` in the appropriate half of the array:
    - If `target >= nums[0]`, perform binary search on the left half of the array.
    - Otherwise, perform binary search on the right half of the array.

```js
var search = function(nums, target) {
    let left = 0, right = nums.length - 1;
    
    // Binary search to find pivot index
    while (left < right) {
        let mid = left + Math.floor((right - left) / 2);
        if (nums[mid] > nums[right]) {
            left = mid + 1;
        } else {
            right = mid;
        }
    }
    
    let pivot = left;
    left = 0;
    right = nums.length - 1;
    
    // Binary search to find target
    while (left <= right) {
        let mid = left + Math.floor((right - left) / 2);
        let realMid = (mid + pivot) % nums.length;
        if (nums[realMid] === target) {
            return realMid;
        } else if (nums[realMid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    
    return -1;
};

```


Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #rotated_array #array #binary_search #leetcode_medium  #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful