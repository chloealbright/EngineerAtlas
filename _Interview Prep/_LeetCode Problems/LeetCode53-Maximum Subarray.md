[Reference](https://leetcode.com/problems/maximum-subarray/description/) 

Find the contiguous subarray within an array of numbers (containing at least one number) that has the largest sum and return that sum.
- **Input**: An array of integers.
- **Output**: The sum of the contiguous subarray with the largest sum.
<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/maximum-subarray/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To solve this problem efficiently, you can use the Kadane's algorithm, which is a dynamic programming approach. The algorithm maintains two variables: `currentMax` and `globalMax`.

Here's a high-level approach to solving Problem 53 using Kadane's algorithm:

1. Initialize `currentMax` and `globalMax` to the first element of the array.
2. Iterate through the array starting from the second element:
    - Update `currentMax` as the maximum of the current element and the sum of the current element and `currentMax`.
    - Update `globalMax` as the maximum of `currentMax` and `globalMax`.
3. After iterating through the array, `globalMax` will contain the maximum sum of the contiguous subarray.

```js
var maxSubArray = function(nums) {
    // Iterative Approach
    let maxSum = nums[0];
    let currentSum = nums[0];
    
    for (let i = 1; i < nums.length; i++) {
        currentSum = Math.max(nums[i], currentSum + nums[i]);
        maxSum = Math.max(maxSum, currentSum);
    }
    
    return maxSum;

};
```

Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]],  #maximum_subarray #array #divide_and_conquer #leetcode_medium #dynamic_programming #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful



