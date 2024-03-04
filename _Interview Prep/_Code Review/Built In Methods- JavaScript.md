### String Methods

1. **String.prototype.split()**:
- LeetCode Problem: Word Break (Problem #139)
- Code Snippet:
```js
const str = "Hello World";
const words = str.split(' ');
console.log(words); // Output: ["Hello", "World"]
```
**Explanation:** Splits a string into an array of substrings based on a specified separator and returns the new array.

2. **String.prototype.indexOf()**:
- LeetCode Problem: Implement strStr() (Problem #28)
- Code Snippet:
```js
const str = "hello";
const index = str.indexOf('e');
console.log(index); // Output: 1

```
**Explanation:** Returns the index within the calling String object of the first occurrence of the specified value, or -1 if not found.

3. **String.prototype.substring()**:
- LeetCode Problem: Longest Palindromic Substring (Problem #5)
- Code Snippet:
```js
const str = "babad";
const substr = str.substring(0, 3);
console.log(substr); // Output: "bab"
```
**Explanation:** Returns a new string containing the characters of the original string from the specified start index (inclusive) to the specified end index (exclusive).

4. **String.prototype.replace()**:
- LeetCode Problem: Reverse Words in a String (Problem #151)
- Code Snippet:
```js
const str = "the sky is blue";
const newStr = str.replace(/\s+/g, ' ').trim();
console.log(newStr); // Output: "blue is sky the"
```
**Explanation:** 
Returns a new string with some or all matches of a pattern replaced by a replacement. In this example, it's replacing multiple consecutive whitespaces with a single space and then trimming the string.

5. **Array.prototype.sort()**:
- LeetCode Problem: Merge Intervals (Problem #56)
- Code Snippet:
```js
const intervals = [[1,3],[2,6],[8,10],[15,18]];
intervals.sort((a, b) => a[0] - b[0]);
console.log(intervals); // Output: [[1,3],[2,6],[8,10],[15,18]]
```
**Explanation:** Sorts the elements of an array in place and returns the sorted array. In this example, it sorts intervals based on their start times.

6. **Array.prototype.join()**:
- LeetCode Problem: Reverse String (Problem #344)
- Code Snippet:
```js
const arr = ["h", "e", "l", "l", "o"];
const str = arr.join('');
console.log(str); // Output: "hello"
```
**Explanation:** Joins all elements of an array into a string. In this example, it joins the characters of the array into a single string.


Updated: March 4th 2024
Related: [[Interview Prep Overview]], [[Languages Overview.canvas|Languages Overview]], #interview_prep #leetcode #quickread