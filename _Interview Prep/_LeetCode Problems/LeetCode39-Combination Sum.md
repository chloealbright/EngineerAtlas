[Reference](https://leetcode.com/problems/combination-sum/description/) 

- **Input**: An array `candidates` of distinct integers representing candidate numbers, and a target integer `target`.
- **Output**: A list of all unique combinations of candidates where the chosen numbers sum to `target`.

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/combination-sum/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To efficiently solve this problem:

- Use backtracking to explore all possible combinations of candidates.
- Keep track of the current combination and the remaining target during the exploration.
- Stop exploring a branch if the remaining target becomes negative.
- Add the current combination to the result when the remaining target becomes zero.

Here's a high-level approach to solving Problem 39:

1. Sort the candidates array to optimize backtracking.
2. Define a backtracking function to explore all possible combinations:
    - Base case: If the remaining target is zero, add the current combination to the result.
    - Recursive case: For each candidate in the candidates array:
        - Add the candidate to the current combination.
        - Recur with the updated combination and the remaining target decreased by the candidate value.
        - Remove the candidate from the current combination to backtrack.

```js
var combinationSum = function(candidates, target) {
    const result = [];
    
    // Sort candidates to optimize backtracking
    candidates.sort((a, b) => a - b);
    
    // Define backtracking function
    const backtrack = (combination, remain, start) => {
        if (remain === 0) {
            result.push([...combination]);
            return;
        }
        if (remain < 0) {
            return;
        }
        for (let i = start; i < candidates.length; i++) {
            combination.push(candidates[i]);
            backtrack(combination, remain - candidates[i], i);
            combination.pop();
        }
    };
    
    // Start backtracking from the beginning
    backtrack([], target, 0);
    
    return result;
};

```


Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #combination_sum #array #backtracking #leetcode_medium  #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful