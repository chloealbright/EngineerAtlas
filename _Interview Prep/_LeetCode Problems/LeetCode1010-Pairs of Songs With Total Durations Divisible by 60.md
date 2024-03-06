[Reference](https://leetcode.com/problems/pairs-of-songs-with-total-durations-divisible-by-60/description/)

Find the number of pairs of songs in a list of song durations where the sum of the durations of each pair is divisible by 60.
- **Input**: An array `time` where `time[i]` represents the duration of the `i`-th song.
- **Output**: The number of pairs of songs whose total duration is divisible by 60.

<body style="margin: 0; overflow: hidden;"> 
<iframe src="https://leetcode.com/problems/pairs-of-songs-with-total-durations-divisible-by-60/description/" style="width: 100%; height: 100vh; border: none;"></iframe> </body>
To solve this problem efficiently, you can use the concept of remainders. 
- You'll iterate through the song durations, 
- calculate the remainder when dividing each duration by 60, 
- and store the frequencies of remainders in a hash map. 
- Then, for each song duration, you'll check how many other durations can be paired with it to form a total duration divisible by 60.

Here's a high-level approach to solving Problem 1010:

1. Initialize a hash map to store the frequencies of remainders when dividing song durations by 60.
2. Iterate through the song durations:
    - Calculate the remainder `r` when dividing each duration by 60.
    - Increment the frequency of `r` in the hash map.
3. Initialize a variable `count` to keep track of the number of valid pairs.
4. Iterate through the song durations again:
    - Calculate the remainder `r` when dividing each duration by 60.
    - If `r` is 0, increment `count` by the frequency of 0 in the hash map.
    - Otherwise, increment `count` by the frequency of `60 - r` in the hash map.
5. Return the value of `count`, which represents the number of valid pairs.

```js
function numPairsDivisibleBy60(time) {
    let count = 0;
    const remainderFreq = new Map();

    for (const duration of time) {
        const remainder = duration % 60;
        const complement = (60 - remainder) % 60;

        if (remainderFreq.has(complement)) {
            count += remainderFreq.get(complement);
        }

        remainderFreq.set(remainder, (remainderFreq.get(remainder) || 0) + 1);
    }

    return count;
}
```
Created: March 4th 2024
Related: [[Interview Prep Overview]], [[DSA Overview]], #pair_of_songs #leetcode_medium #array #hash_table #counting #dsa #leetcode #interview_prep #coding_strategy #leetcode_problem  #insightful 