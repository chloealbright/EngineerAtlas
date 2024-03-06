[Reference](https://leetcode.com/problems/sort-colors/description/) 

- **Input**: An array `nums` containing only 0s, 1s, and 2s.
- **Output**: Sort the array in-place in a single traversal.

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/sort-colors/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To efficiently solve this problem:

- Use the Dutch National Flag Algorithm.
- Initialize three pointers: `low` for 0s, `mid` for 1s, and `high` for 2s.
- Traverse the array and swap elements according to their values and positions.

Here's a high-level approach to solving Problem 75:

1. Initialize three pointers: `low` pointing to the start of the array, `mid` pointing to the start of unsorted 1s, and `high` pointing to the end of the array.
2. Iterate over the array using a while loop until `mid` crosses `high`.
3. If `nums[mid]` is 0, swap it with `nums[low]` and increment both `low` and `mid`.
4. If `nums[mid]` is 1, increment `mid` to skip it as it's already sorted.
5. If `nums[mid]` is 2, swap it with `nums[high]` and decrement `high`.
6. Continue this process until `mid` crosses `high`.
7. At the end of the loop, the array will be sorted in-place.

```js
var sortColors = function(nums) {
    let low = 0, mid = 0, high = nums.length - 1;
    
    while (mid <= high) {
        if (nums[mid] === 0) {
            [nums[low], nums[mid]] = [nums[mid], nums[low]];
            low++;
            mid++;
        } else if (nums[mid] === 1) {
            mid++;
        } else {
            [nums[mid], nums[high]] = [nums[high], nums[mid]];
            high--;
        }
    }
};

```


Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]],  #sort_colors #array #two_pointer #sorting #leetcode_medium #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful