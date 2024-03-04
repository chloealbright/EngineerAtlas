 **Queue Data Structure**: A queue is a linear data structure that follows the First-In-First-Out (FIFO) principle, meaning that the element that is inserted first will be the first to be removed. In JavaScript, a queue can be implemented using an array where elements are added at the end (`push()`) and removed from the beginning (`shift()`), or using a linked list for more efficient enqueue and dequeue operations.

**Example 1**
Initialize an empty queue 
```js
// Shorthand memorization
/*
Queue -> FIFO= first element insterted=first element removed
Implemented using arrays
add elements to the end using push()
remove elements from beginning using shift()

Can use linked list for optimal enqueue & dequeue ops
*/

// Initialize an empty queue
const queue = [];


// Enqueue: Add elements to the end of the queue
queue.push(1);
queue.push(2);
queue.push(3);

// Queue: [1, 2, 3]

// Dequeue: Remove and return the element from the front of the queue
const removedElement = queue.shift();

console.log(removedElement); // Output: 1

// Queue after dequeue: [2, 3]

```

**Example 2**
Initialize the queue with multiple parameters using an array where each element is an array representing a node and its depth.
```js
// Initialize a queue for BFS traversal with root and depth of 1
const queue = [[root, 1]];
let maxDepth = 0;

// Perform BFS traversal
while (queue.length) {
    // Dequeue the front node and its depth
    const [node, depth] = queue.shift();
    // Update maxDepth if current depth is greater
    maxDepth = Math.max(maxDepth, depth);

    // Enqueue left and right children with increased depth
    if (node.left) queue.push([node.left, depth + 1]);
    if (node.right) queue.push([node.right, depth + 1]);
}
```
In addition to the basic operations of initializing, adding, and removing elements from a queue, it's important to understand the following aspects when using a queue in coding problems:

1. **Empty Check**: You should be able to check whether the queue is empty to handle termination conditions in algorithms and prevent errors when attempting to dequeue from an empty queue.
    
2. **Front Element Access**: In some problems, you may need to access the front element of the queue without removing it. This can be useful for inspecting the next element to be processed without modifying the queue.
    
3. **Size Management**: Depending on the problem requirements, you may need to keep track of the size of the queue. This can be useful for monitoring the progress of algorithms or enforcing size limits.
    
4. **Efficiency Consideration**: When solving coding problems, it's important to consider the efficiency of queue operations, especially for large inputs. In JavaScript, using an array as a queue with `push()` and `shift()` operations can lead to inefficient dequeue operations because `shift()` has a time complexity of O(n) as it requires shifting all elements in the array. Alternatively, you can implement a queue using a linked list for more efficient enqueue and dequeue operations.
-------------------------------------------------------

2. **Breadth-First Search (BFS)**: BFS is a graph traversal algorithm that explores all the nodes at the present depth before moving on to the nodes at the next depth level. It's commonly used to traverse tree structures, such as binary trees, in level order. BFS traversal can be implemented iteratively using a queue to store nodes at each level.
    
3. **Queue Operations for BFS**:
    
    - **Enqueue**: Adding an element to the end of the queue. In BFS, enqueue is used to add child nodes to the queue as they are discovered.
    - **Dequeue**: Removing and returning the element from the front of the queue. In BFS, dequeue is used to process nodes at the current level.
    - **Empty Check**: Checking if the queue is empty to determine if traversal is complete.
4. **Using Queue for Level Order Traversal**: In the context of the problem "104. Maximum Depth of Binary Tree," BFS traversal using a queue allows us to visit nodes level by level, ensuring that we can calculate the depth of the tree accurately. By processing nodes level by level, we can increment a depth counter each time we finish processing all nodes at a certain level, effectively determining the maximum depth of the binary tree.


Updated: March 4th 2024
Related: [[LeetCode Canvas.canvas|LeetCode Canvas]], [[DSA Overview]], [[Intro Technical Mock]], [[Common Data Structures.canvas|Common Data Structures]], #dsa #algorithm_design #algorithm_paradigms #insightful 