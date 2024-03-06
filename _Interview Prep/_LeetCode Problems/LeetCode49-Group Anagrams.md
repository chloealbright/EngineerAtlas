[Reference](https://leetcode.com/problems/group-anagrams/description/) 

Group an array of strings into groups of anagrams. 
💡 Two strings are considered *anagrams* if they have the same characters but in a different order.
- **Input**: An array of strings.
- **Output**: A list of groups of anagrams, where each group contains strings that are anagrams of each other.
<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/group-anagrams/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>

To solve this problem efficiently, you can use a hash map to group the strings by their sorted representations. Specifically, you'll iterate through each string, sort its characters, and use the sorted version as a key in the hash map to group anagrams together.

Here's a high-level approach to solving Problem 49:

1. Initialize an empty hash map to store groups of anagrams.
2. Iterate through each string in the input array:
    - Sort the characters of the string.
    - Use the sorted string as a key in the hash map.
    - Append the original string to the list associated with the sorted string in the hash map.
3. Extract the values (lists of strings) from the hash map and return them as the result.

```js
var groupAnagrams = function(strs) {
    const map = new Map();
    
    // Iterate through each string
    for (const str of strs) {
        // Sort the characters to form a unique key
        const key = str.split('').sort().join('');
        
        // Check if the key exists in the map
        if (map.has(key)) {
            map.get(key).push(str);
        } else {
            map.set(key, [str]);
        }
    }
    
    // Return the values of the map
    return [...map.values()];
};

```


Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #group_anagrams #array #hash_table #string #sorting #leetcode_medium #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem #insightful

