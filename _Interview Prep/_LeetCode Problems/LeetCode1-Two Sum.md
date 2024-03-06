[Reference](https://leetcode.com/problems/two-sum/description/) 

Find two numbers in an array that add up to a specific target sum and return their indices.
- **Input**: An array of integers `nums` and an integer `target`.
- **Output**: The indices of the two numbers such that they add up to the target sum.

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/two-sum/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To solve this problem efficiently, you can use a hash map (or JavaScript object) to store the elements of the array along with their indices.

Here's a high-level approach to solving Problem 1:

1. Create an empty hash map to store the elements of the array.
2. Iterate through the array:
    - For each element `nums[i]`, calculate the difference `diff` between the target sum and the current element (`diff = target - nums[i]`).
    - Check if `diff` exists in the hash map. If it does, return the indices `[i, hashMap[diff]]`.
    - If `diff` does not exist in the hash map, store the current element `nums[i]` along with its index `i` in the hash map.
3. If no such pair is found after iterating through the entire array, return an empty array.

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    // Create an empty hash map to store the indices of numbers
    const numMap = new Map();
    
    // Iterate through the array
    for (let i = 0; i < nums.length; i++) {
        // Calculate the difference between the target and the current number
        const diff = target - nums[i];
        
        // Check if the difference exists in the hash map
        if (numMap.has(diff)) {
            // If it exists, return the indices of the two numbers that add up to the target
            return [numMap.get(diff), i];
        }
        
        // If the difference doesn't exist in the hash map, store the current number and its index in the hash map
        numMap.set(nums[i], i);
    }
    
    // If no solution is found, return an empty array
    return [];
};
```



Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #two_sum #array #hash_table #leetcode_easy #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful



