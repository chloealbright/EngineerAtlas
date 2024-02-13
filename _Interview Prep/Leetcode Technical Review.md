[Leetcode Problem 1010- Pairs of Songs With Total Durations Divisible by 60](https://leetcode.com/problems/pairs-of-songs-with-total-durations-divisible-by-60/)

Time Complexity O(n^2)
```js
/**

* @param {number[]} time

* @return {number}

*/

var numPairsDivisibleBy60 = function(time) {

// nested for loop, time complexity O(n^2) quadratic time

// time = [30,20,150,100,40]

// linear search iterate through

// binary divide & conquer search, needs to be sorted first

// q for binary: is the array sorted for every case?

/**

traverse array

add pairs while traversing

then check pair sum % 60 == 0

[cases]

if true: increment counter

  

*/

let count = 0

//iterate through array

for(let start = 0; start < time.length; start++){

//iterate through next point in array

for(let nextNum= start + 1; nextNum < time.length; nextNum++){

if((time[start]+time[nextNum]) % 60 == 0){

++count

}

}

}

  

return count

  

};
```

```js
/**

@param {number[]} time

@return {number}

*/

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

Optimal solution using Maps, time complexity O(n) 
```js
/**

@param {number[]} time

@return {number}

*/

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

Two Sum using Maps O(n)
```js
/**

* @param {number[]} nums

* @param {number} target

* @return {number[]}

*/

var twoSum = function(nums, target) {

let map = new Map()

for (let i = 0; i < nums.length; i++) {

let diff = target - nums[i]

if (map.has(diff)) {

return [i, map.get(diff)]

}

map.set(nums[i], i)

}

};
```
