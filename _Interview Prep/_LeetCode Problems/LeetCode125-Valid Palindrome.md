[Reference](https://leetcode.com/problems/valid-palindrome/) 

- **Input**: A string `s` consisting of alphanumeric characters.
- **Output**: Whether `s` is a valid palindrome, considering only alphanumeric characters and ignoring cases.

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/valid-palindrome/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To efficiently solve this problem, we can use a two-pointer approach:

- Initialize two pointers, `left` and `right`, to the start and end of the string, respectively.
- While `left` is less than `right`:
    - Move `left` pointer to the right until it points to an alphanumeric character.
    - Move `right` pointer to the left until it points to an alphanumeric character.
    - Check if the characters at `left` and `right` pointers are equal (ignoring cases).
        - If not equal, return `false`.
- If the loop completes without finding any unequal characters, return `true`.

Here's a high-level approach to solving Problem 125:

1. Initialize `left` pointer to the start of the string and `right` pointer to the end of the string.
2. While `left` is less than `right`:
    - Move `left` pointer to the right until it points to an alphanumeric character.
    - Move `right` pointer to the left until it points to an alphanumeric character.
    - Check if the characters at `left` and `right` pointers are equal (ignoring cases).
        - If not equal, return `false`.
3. If the loop completes without finding any unequal characters, return `true`.

```js
var isPalindrome = function(s) {
    let left = 0;
    let right = s.length - 1;
    
    while (left < right) {
        while (left < right && !isAlphanumeric(s[left])) left++;
        while (left < right && !isAlphanumeric(s[right])) right--;
        
        if (s[left].toLowerCase() !== s[right].toLowerCase()) return false;
        
        left++;
        right--;
    }
    
    return true;
};

var isAlphanumeric = function(char) {
    return /^[0-9a-zA-Z]+$/.test(char);
};

```

Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #valid_palindrome #string #two_pointer #leetcode_easy  #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful