[Reference](https://leetcode.com/problems/binary-tree-level-order-traversal/description/)

Return the level order traversal of a binary tree's nodes' values. 
   💡*Level order traversal* means visiting the nodes level by level, from left to right.
- **Input**: The root of a binary tree
- **Output**: A 2D array where each sub-array contains the values of nodes at the same level in the binary tree

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/binary-tree-level-order-traversal/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To solve this problem, you can perform a breadth-first search (BFS) traversal of the binary tree. During the BFS traversal, you'll keep track of the nodes at each level and store their values in the result array.

Here's a high-level approach to solving Problem 102:

1. Start with an empty result array to store the level order traversal.
2. Initialize a queue to perform BFS.
3. Add the root node to the queue.
4. While the queue is not empty:
    - Initialize an empty array to store the values of nodes at the current level.
    - Iterate through the nodes in the current level of the queue.
    - Add the value of each node to the array.
    - Enqueue the children of the current nodes (if any) for the next level.
    - Add the array of node values to the result array.
5. Return the result array containing the level order traversal.

```js
/**
 * @param {TreeNode} root
 * @return {number[][]}
 */
var levelOrder = function(root) {
    // Initialize an array to store the result
    const result = [];
    // If the root is null, return an empty array
    if (!root) return result;
    
    // Initialize a queue for BFS traversal
    const queue = [root];
    
    // Perform BFS traversal
    while (root.length) {
        // Store the current level nodes
        const levelNodes = [];
        // Get the number of nodes at the current level
        const levelSize = root.length;
        
        // Traverse all nodes at the current level
        for (let i = 0; i < levelSize; i++) {
            // Dequeue the front node from the queue
            const node = root.shift();
            // Push its value to the current level array
            levelNodes.push(node.val);
            // Enqueue its children if they exist
            if (node.left) root.push(node.left);
            if (node.right) root.push(node.right);
        }
        
        // Push the current level array to the result array
        result.push(levelNodes);
    }
    
    // Return the result array
    return result;
};
```



Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #binary_tree_level #leetcode_medium   #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #binary_tree #tree #bfs #insightful 