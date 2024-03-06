[Reference](https://leetcode.com/problems/spiral-matrix/) 

- **Input**: A 2D matrix `matrix`.
- **Output**: All elements of the matrix in spiral order.

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/spiral-matrix/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To efficiently solve this problem:

- Use four pointers to track the boundaries of the matrix.
- Traverse the matrix in a spiral order by iterating over each layer.

Here's a high-level approach to solving Problem 54:

1. Initialize four pointers to track the boundaries of the matrix: `top`, `bottom`, `left`, and `right`.
2. Initialize an empty array to store the spiral order elements.
3. Loop while `top` is less than or equal to `bottom` and `left` is less than or equal to `right`.
4. Traverse the top row from left to right, adding each element to the result array.
5. Traverse the rightmost column from top to bottom, adding each element to the result array.
6. Traverse the bottom row from right to left, adding each element to the result array.
7. Traverse the leftmost column from bottom to top (excluding the top element), adding each element to the result array.
8. Increment `top`, `bottom`, `left`, and `right`, and repeat steps 4-7 until all elements are traversed.
9. Return the result array containing the elements in spiral order.

```js
var spiralOrder = function(matrix) {
    const result = [];
    let top = 0, bottom = matrix.length - 1, left = 0, right = matrix[0].length - 1;
    
    while (top <= bottom && left <= right) {
        // Traverse top row
        for (let i = left; i <= right; i++) {
            result.push(matrix[top][i]);
        }
        top++;
        
        // Traverse rightmost column
        for (let i = top; i <= bottom; i++) {
            result.push(matrix[i][right]);
        }
        right--;
        
        // Check if there's still a valid bottom row
        if (top <= bottom) {
            // Traverse bottom row
            for (let i = right; i >= left; i--) {
                result.push(matrix[bottom][i]);
            }
            bottom--;
        }
        
        // Check if there's still a valid left column
        if (left <= right) {
            // Traverse leftmost column
            for (let i = bottom; i >= top; i--) {
                result.push(matrix[i][left]);
            }
            left++;
        }
    }
    
    return result;
};

```


Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], 
#spiral_matrix #array #matrix #simulation #leetcode_medium #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful