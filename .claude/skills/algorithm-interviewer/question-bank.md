# Algorithm Interview Question Bank

This file contains reusable algorithm interview questions.

Claude should:

- adapt wording instead of repeating the exact same question
- select questions based on candidate level and weaknesses
- avoid revealing the intended algorithm in the title during interview mode
- use JavaScript by default
- include realistic follow-ups
- sometimes convert abstract problems into real engineering scenarios
- mix traditional and AI-assisted questions

---

# DIFFICULTY

## Easy

One main pattern.

## Medium

Requires pattern recognition plus careful implementation.

## Hard

May combine multiple patterns or require advanced reasoning.

---

# ARRAYS

## Easy

### 1. Find Maximum Value

Given an array of integers, return the largest value.

Example:

Input:
[4, 2, 9, 1, 7]

Output:
9

Follow-ups:

- What if the array is empty?
- Can you do it without sorting?
- Complexity?

---

### 2. Move Zeroes

Given an array, move all zeroes to the end while preserving the order of non-zero values.

Input:
[0, 1, 0, 3, 12]

Output:
[1, 3, 12, 0, 0]

Constraints:
Modify the array in place if possible.

Follow-ups:

- Can you do this in O(n)?
- Can you do it with O(1) extra space?

---

### 3. Remove Duplicates From Sorted Array

Given a sorted array, remove duplicates in place.

Input:
[1, 1, 2, 2, 3]

Result:
[1, 2, 3]

Follow-up:
Why does sorted input make this easier?

---

## Medium

### 4. Product Except Self

Given an array:

[1, 2, 3, 4]

Return:

[24, 12, 8, 6]

Restrictions:
Do not use division.

Follow-ups:

- O(n)?
- O(1) extra space excluding output?

---

# STRINGS

## Easy

### 1. Valid Palindrome

Given a string, determine if it is a palindrome.

Ignore capitalization and non-alphanumeric characters.

Example:

"A man, a plan, a canal: Panama"

Output:
true

Follow-up:
Can you solve it using two pointers?

---

### 2. Valid Anagram

Input:

"listen"
"silent"

Output:
true

Follow-ups:

- Hash Map solution?
- Sorting solution?
- Compare complexity.

---

### 3. First Unique Character

Given a string, return the index of the first character that appears exactly once.

Input:
"leetcode"

Output:
0

---

# HASH MAP / HASH SET

## Easy

### 1. Contains Duplicate

Given:

[1, 2, 3, 1]

Return:
true

Ask candidate for:

- brute force
- Hash Set optimization
- time and space complexity

---

### 2. Two Sum

Given:

nums = [2, 7, 11, 15]
target = 9

Return:
[0, 1]

Candidate should first discuss brute force.

Follow-up:
Can we solve this in O(n)?

---

### 3. Character Frequency

Given a string, return how many times each character appears.

Input:

"banana"

Possible output:

{
b: 1,
a: 3,
n: 2
}

---

## Medium

### 4. Group Anagrams

Input:

["eat", "tea", "tan", "ate", "nat", "bat"]

Group equivalent anagrams.

Follow-ups:

- What could be used as a Map key?
- Sorting characters versus frequency representation?

---

### 5. Longest Consecutive Sequence

Input:

[100, 4, 200, 1, 3, 2]

Output:
4

Because:

1, 2, 3, 4

Target:
O(n)

---

# TWO POINTERS

## Easy

### 1. Sorted Two Sum

Given a sorted array:

[1, 2, 4, 6, 10]

target = 8

Find the pair.

Candidate should recognize that sorted input can remove the need for a Hash Map.

---

### 2. Palindrome With Two Pointers

Check whether a string is a palindrome without creating a reversed copy.

---

## Medium

### 3. Container Capacity

Given heights representing vertical boundaries, find the maximum area formed by two boundaries.

Evaluate:

- why moving one pointer works
- complexity
- reasoning

---

# BINARY SEARCH

## Easy

### 1. Find Target

Given a sorted array:

[2, 4, 7, 10, 15, 21]

target = 15

Return:
4

Expected:
O(log n)

Follow-ups:

- target missing
- one-element input
- first element
- last element

---

### 2. Search Insert Position

Input:

nums = [1, 3, 5, 6]
target = 2

Output:
1

Follow-up:
How is this different from exact binary search?

---

## Medium

### 3. First Occurrence

Input:

[1, 2, 2, 2, 4, 5]

target = 2

Return:
1

Important:
Finding any `2` is not sufficient.

---

### 4. Last Occurrence

Input:

[1, 2, 2, 2, 4, 5]

target = 2

Return:
3

---

### 5. Earliest Broken Deployment

Versions:

1 ... N

API:

isBroken(version)

Behavior is monotonic:

working working working broken broken broken

Find the first broken version using the fewest API calls.

Real-world constraints:
API calls are expensive.

Expected:
O(log n)

---

### 6. Maximum Safe Server Load

You have:

canHandle(concurrentUsers)

Returns:
true if healthy
false if overloaded

Assume once the server fails at N users, all larger values also fail.

Find maximum safe load.

Expected:
Binary search over answer space.

---

## Hard

### 7. Search Rotated Sorted Array

Input:

[4, 5, 6, 7, 0, 1, 2]

target:
0

Return:
4

Ask candidate:
Which half is guaranteed to be sorted?

---

# SLIDING WINDOW

## Easy

### 1. Maximum Sum of K Consecutive Elements

Input:

[2, 1, 5, 1, 3, 2]

k = 3

Output:
9

Because:
5 + 1 + 3 = 9

Ask:
What repeated work does brute force perform?

---

## Medium

### 2. Longest Substring Without Repeating Characters

Input:

"abcabcbb"

Output:
3

Because:
"abc"

Ask candidate to explain:

- left pointer
- right pointer
- what makes window invalid

---

### 3. Minimum Length Subarray

Given positive integers and a target sum, find the minimum contiguous subarray whose sum is at least target.

---

# STACK

## Easy

### 1. Valid Parentheses

Input:

"({[]})"

Output:
true

Ask:
Why is Stack appropriate?

---

### 2. Browser History

Design a simple navigation model supporting:

visit
back

Discuss why Stack-like behavior appears.

---

## Medium

### 3. Next Greater Element

For each value, find the next value to the right that is larger.

Potential follow-up:
Can you improve O(n²)?

---

# QUEUE / BFS

## Easy

### 1. Level Order Traversal

Given a binary tree, return values level by level.

Expected:
Queue / BFS

---

### 2. Customer Support Queue

Customers arrive sequentially.

Process them in arrival order.

Discuss:
Queue versus Stack.

---

# LINKED LISTS

## Easy

### 1. Reverse Linked List

Input:

1 → 2 → 3 → 4

Output:

4 → 3 → 2 → 1

Evaluate:

- prev
- current
- next

---

### 2. Find Middle Node

Use:
slow pointer
fast pointer

Ask:
Why does fast moving 2× find the middle?

---

## Medium

### 3. Detect Cycle

Determine whether a linked list contains a cycle.

Expected:
Fast and Slow Pointers

Follow-up:
Why does this work without extra memory?

---

# TREES

## Easy

### 1. Maximum Depth

Given a binary tree, return its maximum depth.

Allow:
DFS
or
BFS

Ask candidate to compare both.

---

### 2. Tree Traversal

Implement:

- preorder
- inorder
- postorder

Ask what order each uses.

---

## Medium

### 3. Validate Binary Search Tree

Determine whether a binary tree satisfies BST rules.

Watch for incorrect approach:
Only comparing node with immediate children.

---

### 4. Lowest Common Ancestor

Given two nodes, find their lowest common ancestor.

---

# HEAP / PRIORITY QUEUE

## Medium

### 1. Kth Largest Element

Input:

[3, 2, 1, 5, 6, 4]

k = 2

Output:
5

Ask candidate:
Sorting vs Heap?

---

### 2. Top K Products

A commerce platform receives millions of sales events.

Continuously return the top 10 products.

Discuss:
Why not sort everything after every event?

Expected:
Heap.

---

# GRAPHS

## Easy

### 1. Reachability

Given a graph and two nodes, determine whether a path exists.

Allow:
DFS or BFS

Ask:
What prevents infinite loops?

Expected:
visited set.

---

## Medium

### 2. Number of Islands

Given a grid of water and land, count connected land regions.

Expected:
DFS or BFS.

---

### 3. Shortest Connection Between Users

Users are nodes.

Friendships are edges.

Find the minimum number of connections between two users.

Expected:
BFS for unweighted graph.

---

### 4. Dependency Cycle

Microservices have dependencies.

Determine whether there is a dependency cycle.

Expected:
Graph cycle detection / topological approach.

---

### 5. Course Scheduling

Some courses require prerequisites.

Determine whether all courses can be completed.

Expected:
Topological sort / cycle detection.

---

# BACKTRACKING

## Medium

### 1. Generate All Subsets

Input:

[1, 2, 3]

Generate all subsets.

Teach:

choose
→ explore
→ undo

---

### 2. Generate Permutations

Input:

[1, 2, 3]

Return all permutations.

---

### 3. Combination Sum

Find combinations that reach target.

Evaluate:

- decision tree
- pruning
- backtracking

---

# DYNAMIC PROGRAMMING

## Easy

### 1. Climbing Stairs

You can climb 1 or 2 stairs at a time.

How many ways are there to reach step N?

Ask:
What smaller results are repeated?

---

### 2. House Robber

Each house contains money.

Adjacent houses cannot both be robbed.

Find maximum obtainable amount.

Teach:
choose current
vs
skip current

---

## Medium

### 3. Coin Change

Given coin values and target amount, find minimum number of coins.

Discuss:
state
transition
base case

---

### 4. Grid Paths

Count possible paths from top-left to bottom-right.

---

# INTERVALS

## Medium

### 1. Merge Intervals

Input:

[[1,3],[2,6],[8,10],[15,18]]

Output:

[[1,6],[8,10],[15,18]]

Ask:
Why might sorting be useful first?

---

### 2. Meeting Room Conflicts

Given meeting intervals, determine whether one person can attend all meetings.

Real-world framing.

---

# PREFIX SUM

## Easy / Medium

### 1. Range Sum Queries

Array:

[2, 4, 1, 7, 3]

You receive thousands of queries:

sum(left, right)

Ask:
Should we recompute every range from scratch?

Expected:
Prefix Sum.

---

# GREEDY

## Medium

### 1. Meeting Selection

Given meetings with start/end times, attend as many as possible.

Ask:
What local choice might lead to maximum count?

---

# TOPOLOGICAL SORT

## Medium

### Deployment Dependencies

Services:

API → Database
Frontend → API
Analytics → Database

Find a valid deployment order.

Follow-up:
What if dependencies contain a cycle?

---

# AI-ASSISTED INTERVIEW BANK

These should not always ask the candidate to implement from scratch.

---

## AI Type 1 — Review Correct Code

Give correct AI code.

Ask candidate to:

- explain it
- derive complexity
- test it
- identify assumptions

---

## AI Type 2 — Find AI Bug

Problem:
Classic Binary Search

AI returns:

```js
function binarySearch(nums, target) {
  let left = 0;
  let right = nums.length - 1;

  while (left < right) {
    const mid = Math.floor((left + right) / 2);

    if (nums[mid] === target) {
      return mid;
    }

    if (nums[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }

  return -1;
}
```

## Source: AlgoMonster

Pattern: Binary Search
Difficulty: Easy
Problem: Search Insert Position
Source URL: ...
Status: not_started
