[Reference](https://leetcode.com/problems/reverse-words-in-a-string/description/) 

Reverse the order of words in a given string.
- **Input:** A string `s` containing words separated by spaces. 
- **Output:** A string with the words reversed, where multiple spaces between words are reduced to a single space, and leading/trailing spaces are removed.

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/reverse-words-in-a-string/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>
To solve this problem, we can split the input string into an array of words, reverse the array, and then join the words back together into a string.

Here's a high-level approach to solving Problem 151:

1. Split the input string `s` into an array of words using the `split` method, specifying the space character as the delimiter.
2. Reverse the array of words.
3. Join the reversed array of words into a string using the `join` method, specifying a single space character as the separator.
4. Return the resulting string.

```js
var reverseWords = function(s) {
    // Trim leading and trailing spaces from the input string
    s = s.trim();
    let reversed = ''; // Initialize an empty string to store the reversed words
    let word = ''; // Initialize an empty string to store each word
    
    // Iterate through each character in the trimmed input string
    for (let i = 0; i < s.length; i++) {
        // If the current character is not a space, append it to the word
        if (s[i] !== ' ') {
            word += s[i];
        } else {
            // If the current character is a space and the word is not empty,
            // append the reversed word to the beginning of the result string
            if (word !== '') {
                reversed = word + ' ' + reversed;
                word = ''; // Reset the word for the next word
            }
        }
    }
    // Append the last word to the beginning of the result string
    reversed = word + ' ' + reversed;
    // Trim any leading or trailing spaces from the result string and return it
    return reversed.trim();
};

```


Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #string #two_pointer #reverse_words #leetcode_medium  #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful