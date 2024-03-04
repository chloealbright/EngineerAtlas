**Recursive Algorithms**:

- Recursive algorithms are characterized by the process of solving a problem by breaking it down into smaller instances of the same problem.
- Each recursive call reduces the problem size until it reaches a base case, where the solution is known without further recursion.
- Recursion can be visualized as a set of nested function calls, with each call contributing to the solution of the larger problem.
- Examples of problems often solved using recursion include tree traversal, dynamic programming, and backtracking.

**Example**
Use recursion to traverse a binary tree and print the values of its nodes using a depth-first approach.

```js
// Definition for a binary tree node
function TreeNode(val) {
    this.val = val;
    this.left = this.right = null;
}

// Recursive function to traverse a binary tree in depth-first manner (Preorder traversal)
function dfs(node) {
    // Base case: If the current node is null, return
    if (!node) return;

    // Print the value of the current node
    console.log(node.val);

    // Recursive call for left subtree
    dfs(node.left);

    // Recursive call for right subtree
    dfs(node.right);
}

// Example usage
// Constructing a binary tree
const root = new TreeNode(1);
root.left = new TreeNode(2);
root.right = new TreeNode(3);
root.left.left = new TreeNode(4);
root.left.right = new TreeNode(5);

// Traverse the binary tree using depth-first search (Preorder traversal)
dfs(root);

```

#### Explanation:

1. We define a `TreeNode` class to represent nodes in the binary tree. Each node has a `val` (value) and references to its left and right children.
2. We define a recursive function `dfs` to traverse the binary tree in a depth-first manner (Preorder traversal).
3. In the `dfs` function:
    - We have a base case: if the current node is null, we return, terminating the recursion.
    - We print the value of the current node.
    - We recursively call `dfs` for the left subtree and then for the right subtree.
4. We construct an example binary tree and traverse it using the `dfs` function.

#### Steps to Memorize Recursion for Coding Problems:

1. **Understand the Problem**: Fully understand the problem statement and the requirements. Identify if recursion is an appropriate approach for solving the problem.
2. **Identify Base Cases**: Determine the base cases where the recursion should terminate. These are typically simple cases that can be solved directly.
3. **Define Recursive Function**: Define a recursive function that solves the problem. This function should handle the general case and make recursive calls to smaller subproblems.
4. **Trace the Recursion**: Mentally or physically trace through the recursive calls with small inputs. Understand how the recursion progresses towards the base cases and how it combines the results of smaller subproblems.
5. **Code the Solution**: Write the recursive function based on the defined steps, ensuring that the base cases are properly handled and the recursive calls are made on smaller instances of the problem.
6. **Test the Solution**: Test the recursive function with various inputs, including edge cases, to ensure that it produces the correct results and terminates correctly.

Breaking down recursion into these steps helps in understanding the problem, designing a solution, and implementing it effectively. With practice and familiarity, recursion becomes easier to comprehend and utilize in coding problems.

Updated: March 4th 2024
Related: [[LeetCode Canvas.canvas|LeetCode Canvas]], [[DSA Overview]], [[Intro Technical Mock]], #dsa #algorithm_design #algorithm_paradigms #quickread
