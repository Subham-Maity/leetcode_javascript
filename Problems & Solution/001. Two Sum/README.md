

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


### What is a hash table?
- A hash table is a way of storing and finding data using keys and values. 
- A key is something that identifies the data, like a name or a word. A value is the data itself, like a phone number or a definition. 
- For example, if you have a dictionary of words and their meanings, you can use a hash table to store them and find them quickly.

### Why use a hash table?
- We use a hash table when we want to perform fast and efficient operations on a large amount of data, such as searching, inserting, deleting, or updating.
- We use a hash table because it can reduce the time complexity of searching from O(n) to O(1) on average, where n is the number of elements in the data set.
- This means that we can find the value for any key in constant time, regardless of how many elements are in the data set.

### How does a hash table work?
- A hash table uses an array to store the values. An array is a way of storing data in order using numbers. 
- For example, if you have an array of size 10, you can store 10 values in it using numbers from 0 to 9. The number is called an index or a position.
- A hash table also uses a hash function to find the index for each key. A hash function is a way of turning a key into a number. 
- For example, if you have a word "cat", you can use a hash function to turn it into a number like 3. The number is called a hash code or an index.
- To store the value for a key, you can use the hash function to find the index for the key, and then store the value in the array at that index. 
- For example, if you have a word "cat" and its meaning "a small furry animal", you can use the hash function to turn "cat" into 3, and then store "a small furry animal" in the array at index 3.
- To find the value for a key, you can use the same hash function to find the index for the key, and then look at the array at that index. 
- For example, if you want to find the meaning for "cat", you can use the hash function to turn "cat" into 3, and then look at the array at index 3 to get "a small furry animal".

### What are some advantages and disadvantages of using a hash table?
- Some advantages of using a hash table are:
  - It can perform fast and efficient operations on large data sets.
  - It can store any type of data as keys and values, such as numbers, strings, objects, etc.
  - It can handle dynamic resizing of the data set without affecting the performance significantly.
- Some disadvantages of using a hash table are:
  - It requires extra space to store the elements in the array and the hash function.
  - It can have collisions when two different keys have the same index. This can make it hard to find the right value for a key.
  - It can be difficult to choose a good hash function that minimizes collisions and distributes the keys evenly in the array.
### One pass and two pass hash table
- One pass and two pass hash table are techniques to solve problems where we need to find two elements in an array that satisfy some condition, such as adding up to a target value.
- One pass hash table works as follows:
  - In one pass, we iterate over the array and for each element, we check if its complement (the value that satisfies the condition with the current element) exists in the hash table. If it does exist, we return the current element's index and its complement's index as a solution.
  - If the complement does not exist, we add the current element's value as a key and its index as a value to the hash table.
- Two pass hash table works as follows:
  - In the first pass, we iterate over the array and add each element's value as a key and its index as a value to the hash table.
  - In the second pass, we iterate over the array again and for each element, we check if its complement (the value that satisfies the condition with the current element) exists in the hash table. If it does exist, we return the current element's index and its complement's index as a solution.
  
## ⌛ Time Taken To Solve(mine)

- [ ] Less than 10 minutes
- [x] 10 - 30 minutes
- [ ] 30 - 60 minutes
- [ ] More than an hour





