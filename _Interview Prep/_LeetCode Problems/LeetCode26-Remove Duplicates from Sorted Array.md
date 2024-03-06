[Reference](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/) 


- **Input**: A sorted array `nums` of integers.
- **Output**: The length of the modified array after removing duplicates. The modified array should contain only unique elements in sorted order.
<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To efficiently solve this problem and modify the array in-place:

- Initialize a pointer `i` to 0 to keep track of the current unique element.
- Iterate through the array with another pointer `j`, starting from the second element.
- Compare the element at `j` with the element at `i`:
    - If they are equal, increment `j` to move to the next element.
    - If they are not equal:
        - Increment `i`.
        - Copy the element at `j` to the position `i`.
        - Increment `j` to move to the next element.
- After the iteration, return `i + 1`, which represents the length of the modified array containing unique elements.

Here's a high-level approach to solving Problem 26:

1. Initialize a pointer `i` to 0 to keep track of the current unique element.
2. Iterate through the array with another pointer `j`, starting from the second element.
    - Compare the element at `j` with the element at `i`.
        - If they are equal, increment `j`.
        - If they are not equal:
            - Increment `i`.
            - Copy the element at `j` to the position `i`.
            - Increment `j`.
3. After the iteration, return `i + 1`, which represents the length of the modified array containing unique elements.

```js
var removeDuplicates = function(nums) {
    if (nums.length === 0) return 0;
    
    let i = 0;
    for (let j = 1; j < nums.length; j++) {
        if (nums[j] !== nums[i]) {
            i++;
            nums[i] = nums[j];
        }
    }
    
    return i + 1;
};

```


Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #reverse_duplicates #array #two_pointer #leetcode_easy  #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful