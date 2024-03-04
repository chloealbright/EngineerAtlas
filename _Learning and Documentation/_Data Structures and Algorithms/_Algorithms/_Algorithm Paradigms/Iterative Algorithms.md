**Iterative Algorithms**:

- Iterative algorithms, on the other hand, involve a repetitive process where the solution is reached through a series of iterations or loops.
- They typically involve looping constructs such as `for` loops, `while` loops, or `do-while` loops to repeatedly execute a set of instructions until a certain condition is met.
- Unlike recursion, iterative algorithms do not involve function calls that create additional stack frames, making them potentially more memory-efficient for problems with large input sizes.
- Iterative algorithms are often used in situations where the problem can be solved incrementally or where the solution can be derived through a sequence of steps.

**Example**
Use an iterative approach to traverse a binary tree in level order (breadth-first traversal) using a queue.

```js
// Definition for a binary tree node
function TreeNode(val) {
    this.val = val;
    this.left = this.right = null;
}

// Function to perform level order traversal iteratively
function levelOrder(root) {
    // Initialize an empty array to store the result
    const result = [];
    
    // If root is null, return empty result
    if (!root) return result;
    
    // Initialize a queue for BFS traversal
    const queue = [root];
    
    // Perform BFS traversal
    while (queue.length) {
        // Initialize an array to store nodes at current level
        const levelNodes = [];
        // Get the number of nodes at current level
        const levelSize = queue.length;
        
        // Traverse all nodes at current level
        for (let i = 0; i < levelSize; i++) {
            // Dequeue the front node from the queue
            const node = queue.shift();
            // Add its value to current level array
            levelNodes.push(node.val);
            // Enqueue its children if they exist
            if (node.left) queue.push(node.left);
            if (node.right) queue.push(node.right);
        }
        
        // Push the current level array to the result array
        result.push(levelNodes);
    }
    
    // Return the result array containing level order traversal
    return result;
}

// Example usage
// Constructing a binary tree
const root = new TreeNode(3);
root.left = new TreeNode(9);
root.right = new TreeNode(20);
root.right.left = new TreeNode(15);
root.right.right = new TreeNode(7);

// Perform level order traversal
console.log(levelOrder(root)); // Output: [[3], [9, 20], [15, 7]]

```

#### Explanation:

1. We define a function `levelOrder` to perform level order traversal of a binary tree iteratively.
2. We initialize an empty array `result` to store the result of level order traversal.
3. If the `root` is null, we return an empty result.
4. We initialize a queue `queue` for BFS traversal and enqueue the `root` node.
5. We perform BFS traversal using a while loop until the queue is empty:
    - Inside the loop, we initialize an empty array `levelNodes` to store nodes at the current level.
    - We get the number of nodes at the current level using `levelSize` which is the current size of the queue.
    - We iterate through all nodes at the current level:
        - Dequeue the front node from the queue.
        - Add its value to the `levelNodes` array.
        - Enqueue its left and right children if they exist.
    - After processing all nodes at the current level, we push the `levelNodes` array to the `result` array.
6. Finally, we return the `result` array containing the level order traversal.

#### Steps to Memorize the Iterative Approach:

1. **Understand the Problem**: Clearly understand the problem statement and the desired output.
2. **Identify Iterative Approach**: Determine if an iterative approach is suitable for solving the problem. For problems involving traversal or search, iterative approaches like BFS or DFS are often applicable.
3. **Select Data Structure**: Choose an appropriate data structure to support the iterative algorithm. For BFS traversal, a queue is commonly used.
4. **Initialize Variables**: Initialize any necessary variables or data structures before starting the iterative process.
5. **Perform Iteration**: Use loops (e.g., `while` loop, `for` loop) to iterate through elements or perform repetitive tasks. Update variables and data structures accordingly during each iteration.
6. **Handle Termination Condition**: Ensure the iteration terminates correctly based on the problem requirements. This may involve breaking out of the loop or returning the result.
7. **Test the Solution**: Test the iterative solution with various inputs, including edge cases, to ensure correctness and efficiency.

Breaking down the iterative approach into these steps helps in understanding the problem-solving process and writing clear and efficient code. With practice and familiarity, iterative algorithms become easier to implement and apply to different coding problems.



Updated: March 4th 2024
Related: [[LeetCode Canvas.canvas|LeetCode Canvas]], [[DSA Overview]], [[Intro Technical Mock]], #dsa #algorithm_design #algorithm_paradigms #quickread