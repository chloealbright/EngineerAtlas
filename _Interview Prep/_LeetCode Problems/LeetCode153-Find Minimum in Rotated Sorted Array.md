[Reference](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/description/) 

 Find the smallest element in a rotated sorted array. The array is initially sorted in ascending order but is rotated at some pivot point unknown to us.
- **Input**: An array `nums` of distinct integers sorted in ascending order, which has been rotated at some pivot unknown to you.
- **Output**: The minimum element of `nums`.

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To solve this problem efficiently, we can use a binary search approach:

- Initialize two pointers, `left` and `right`, to the start and end of the array, respectively.
- While `left` is less than `right`:
    - Find the middle element (`mid`) of the array.
    - Check if `nums[mid]` is less than `nums[right]`:
        - If true, update `right = mid`.
        - If false, update `left = mid + 1`.
- Return `nums[left]`, which represents the minimum element.

Here's a high-level approach to solving Problem 153:

1. Initialize `left` pointer to 0 and `right` pointer to `nums.length - 1`.
2. While `left` is less than `right`:
    - Calculate `mid` as the middle index of the array.
    - Check if `nums[mid]` is less than `nums[right]`:
        - If true, update `right = mid`.
        - If false, update `left = mid + 1`.
3. Return `nums[left]` as the minimum element.

```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var findMin = function(nums) {
    let left = 0;
    let right = nums.length - 1;
    
    // Perform binary search
    while (left < right) {
        const mid = Math.floor((left + right) / 2);
        
        // Check if the mid element is greater than the rightmost element
        if (nums[mid] > nums[right]) {
            // If true, the minimum element is to the right of mid
            left = mid + 1;
        } else {
            // If false, the minimum element is to the left of mid or mid itself
            right = mid;
        }
    }
    
    // When left and right pointers converge, the minimum element is found
    return nums[left];
};

```

Explanation to practice recall of the problem:

- We initialize two pointers, `left` and `right`, representing the start and end indices of the array, respectively.
- We perform binary search by iterating until `left` is less than `right`.
- In each iteration, we calculate the `mid` index.
- We compare the element at the `mid` index with the element at the `right` index.
- If `nums[mid]` is greater than `nums[right]`, it means the minimum element is to the right of `mid`, so we update `left = mid + 1`.
- If `nums[mid]` is not greater than `nums[right]`, the minimum element is to the left of `mid` or `mid` itself, so we update `right = mid`.
- When the loop ends, `left` and `right` converge, and we return `nums[left]`, which represents the minimum element in the array.

Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #find_minimum #leetcode_medium  #array #binary_search #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful