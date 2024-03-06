[Reference](https://leetcode.com/problems/simplify-path/description/) 

- **Input**: A string `path` representing an absolute path.
- **Output**: The simplified canonical path.

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/simplify-path/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To efficiently solve this problem:

- Split the input path into its components using the `/` delimiter.
- Use a stack to keep track of the canonical path.
- Iterate over the components and process each accordingly.

Here's a high-level approach to solving Problem 71:

1. Split the input `path` into its components using the `/` delimiter.
2. Initialize an empty stack to keep track of the canonical path.
3. Iterate over the components of the path.
4. If the current component is `".."`, pop the top element from the stack (if the stack is not empty).
5. If the current component is `"."` or an empty string, continue to the next component.
6. Otherwise, push the current component onto the stack.
7. After processing all components, construct the simplified canonical path using the elements in the stack.
8. Join the elements in the stack with `/` as the delimiter to form the simplified canonical path.
9. Return the simplified canonical path.

```js
var simplifyPath = function(path) {
    const components = path.split('/');
    const stack = [];
    
    for (const component of components) {
        if (component === '..') {
            stack.pop();
        } else if (component && component !== '.') {
            stack.push(component);
        }
    }
    
    return '/' + stack.join('/');
};

```


Created: March 6th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #simplify_path #string #stack #leetcode_medium  #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful