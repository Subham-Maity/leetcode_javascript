

# 🎯 Two Sum - LeetCode(JavaScript)



- [**🔗 Problem Link**](https://leetcode.com/problems/two-sum/)


### 🌐 Read On Website(Better Experience)

- [**👉 Read On My Website(Best)**](http://codexam.vercel.app/docs/leetcode/lc1)
- [**👉 Read On Hashnode**](https://codexam.hashnode.dev/)
- [**👉 Read On Dev.to**](https://dev.to/codexam)


#### 📊 Difficulty Level

- [x] Easy
- [ ] Medium
- [ ] Hard
- [ ] Expert

> ---
> ---



## 💥 Brute Force Solution

### 🧠 Approach
- The brute-force approach is to loop through the array and for each element, check if there is another element that adds up to the target.
- To do this, we can use a nested loop that iterates over the array from the current index to the end and compares the sum of the current element and the next element with the target.
- If the sum is equal to the target, we return an array with the indices of the two elements.
- If we reach the end of the loop without finding a pair that matches the target, we return an empty array.




### 📝 Pseudocode
```js
// Define a function that takes an array of numbers and a target number as parameters using an arrow function syntax
const twoSum = (nums, target) => {
  // Loop through the array from the first element to the second last element
  for (let i = 0; i < nums.length - 1; i++) {
    // Loop through the array from the next element to the last element
    for (let j = i + 1; j < nums.length; j++) {
      // Check if the sum of the current element and the next element is equal to the target
      if (nums[i] + nums[j] === target) {
        // If yes, return an array with their indices
        return [i, j];
      }
    }
  }
  // If no pair is found, return an empty array
  return [];
}
```
- **⏰ Time complexity**: The time complexity of this approach is O(n^2), where n is the length of the array. This is because we have to loop through the array twice and compare each pair of elements.
- **💾 Space complexity**: The space complexity of this approach is O(1), because we only use constant extra space to store the indices.

---

## 🚀 Better Solution

### 🧠 Approach
- The two-pass hash table approach is to use a hash table (or an object in JavaScript) to store the mapping of each element in the array to its index.
- In the first pass, we iterate over the array and add each element's value as a key and its index as a value to the hash table.
- In the second pass, we iterate over the array again and for each element, we check if its complement (target - element) exists in the hash table. If it does exist, we return the current element's index and its complement's index as an array.
- We also make sure that the complement is not the same as the current element, because we cannot use the same element twice.



### 📝 Pseudocode

```javascript
// Function to find two numbers that add up to a target using a two-pass hash table
function twoSum(nums, target) {
  // Create an empty hash table (or an object in JavaScript)
  let map = {};
  // Loop over the array and add each element's value as a key and its index as a value to the hash table
  for (let i = 0; i < nums.length; i++) {
    map[nums[i]] = i;
  }
  // Loop over the array again
  for (let i = 0; i < nums.length; i++) {
    // Calculate the complement of the current element
    let complement = target - nums[i];
    // Check if the complement exists in the hash table and is not the same as the current element
    if (map.hasOwnProperty(complement) && map[complement] !== i) {
      // Return the current element's index and its complement's index as an array
      return [i, map[complement]];
    }
  }
  // Return an empty array if no solution is found
  return [];
}
```

- **⏰ Time complexity**: The time complexity of this approach is O(n), where n is the length of the array, because we have to iterate over the array twice and each lookup in the hash table takes O(1) time on average.
- **💾 Space complexity**: The space complexity of this approach is O(n), because we have to store n elements in the hash table.

---

## 🏆 Optimal Solution

### 🧠 Approach

- The approach is to use a hash table (or an object in JavaScript) to store the mapping of each element in the array to its index.
> Hash Table use because it has O(1) time complexity for insertion, deletion and lookup.
- In one pass, we iterate over the array and for each element, we check if its complement (target - element) exists in the hash table. If it does exist, we return the current element's index and its complement's index as an array.
- If the complement does not exist, we add the current element's value as a key and its index as a value to the hash table.
- We also make sure that the complement is not the same as the current element, because we cannot use the same element twice.

### 📝 Pseudocode

```js

// Function to find two numbers that add up to a target using a one-pass hash table
function twoSum(nums, target) {
  // Create an empty hash table (or an object in JavaScript)
  let map = {};
  // Loop over the array
  for (let i = 0; i < nums.length; i++) {
    // Calculate the complement of the current element
    let complement = target - nums[i];
    // Check if the complement exists in the hash table and is not the same as the current element
    if (map.hasOwnProperty(complement) && map[complement] !== i) {
      // Return the current element's index and its complement's index as an array
      return [i, map[complement]];
    }
    // If the complement does not exist, add the current element's value as a key and its index as a value to the hash table
    map[nums[i]] = i;
  }
  // Return an empty array if no solution is found
  return [];
}
```
- **⏰ Time complexity**: The time complexity of this approach is O(n), where n is the length of the array, because we have to iterate over the array once and each lookup and insertion in the hash table takes O(1) time on average.
- **💾 Space complexity**: The space complexity of this approach is O(n), because we have to store n elements in the hash table.

---

## 📝 Conclusion

- In this problem, we have learned how to find two numbers that add up to a target in an array of integers.
- We have explored three different approaches: brute-force, two-pass hash table, and one-pass hash table.
- We have analyzed the time and space complexity of each approach and compared their advantages and disadvantages.
- We have implemented each approach in JavaScript and Python and tested them with some examples.
- We have concluded that the one-pass hash table approach is the optimal solution because it has the lowest time complexity of O(n) and uses only O(n) extra space.

## 📚 References

### Hash table data structure
- A hash table is a data structure that implements an associative array or dictionary. It is an abstract data type that maps keys to values¹.
- A hash table uses a hash function to compute an index, also called a hash code, into an array of buckets or slots, from which the desired value can be found¹.
- A hash table is a data structure that is used to store key/value pairs. It uses a hash function to compute an index into an array in which an element will be inserted or searched. By using a good hash function, hashing can work well. Under reasonable assumptions, the average time required to search for an element in a hash table is O(1)⁵.

### When and why we use hash table
- We use hash table when we want to perform fast and efficient operations on a large amount of data, such as searching, inserting, deleting, or updating².
- We use hash table because it offers the following advantages²:
  - It can reduce the time complexity of searching from O(n) to O(1) on average, where n is the number of elements in the data set.
  - It can store any type of data as keys and values, such as numbers, strings, objects, etc.
  - It can handle dynamic resizing of the data set without affecting the performance significantly.

### Two-pass hash table
- A two-pass hash table is a technique to solve problems where we need to find two elements in an array that satisfy some condition, such as adding up to a target value³.
- A two-pass hash table works as follows³:
  - In the first pass, we iterate over the array and add each element's value as a key and its index as a value to the hash table.
  - In the second pass, we iterate over the array again and for each element, we check if its complement (the value that satisfies the condition with the current element) exists in the hash table. If it does exist, we return the current element's index and its complement's index as a solution.
- A two-pass hash table has the following advantages and disadvantages³:
  - Advantages:
    - It is easy to implement and understand.
    - It has a linear time complexity of O(n), where n is the length of the array.
    - It can handle negative numbers and duplicates in the array.
  - Disadvantages:
    - It requires extra space of O(n) to store the elements in the hash table.
    - It requires two iterations over the array, which can be inefficient for large data sets.

### One-pass hash table
- A one-pass hash table is a technique to solve problems where we need to find two elements in an array that satisfy some condition, such as adding up to a target value⁴.
- A one-pass hash table works as follows⁴:
  - In one pass, we iterate over the array and for each element, we check if its complement (the value that satisfies the condition with the current element) exists in the hash table. If it does exist, we return the current element's index and its complement's index as a solution.
  - If the complement does not exist, we add the current element's value as a key and its index as a value to the hash table.
- A one-pass hash table has the following advantages and disadvantages⁴:
  - Advantages:
    - It has a linear time complexity of O(n), where n is the length of the array.
    - It requires only one iteration over the array, which can be more efficient for large data sets.
    - It can handle negative numbers and duplicates in the array.
  - Disadvantages:
    - It requires extra space of O(n) to store the elements in the hash table.
    - It can be more difficult to implement and understand than a two-pass hash table.

## ⌛ Time Taken To Solve(mine)

- [ ] Less than 10 minutes
- [x] 10 - 30 minutes
- [ ] 30 - 60 minutes
- [ ] More than an hour





