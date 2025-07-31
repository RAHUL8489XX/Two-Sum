# 🧮 Two Sum — LeetCode Problem Solution

## 🚀 Overview
This repository contains a clean and optimized solution to the classic [LeetCode "Two Sum"](https://leetcode.com/problems/two-sum) problem. Given a list of integers and a target sum, the goal is to identify two distinct indices whose values sum up to the target.

This solution is implemented in Python and leverages a hash map for O(n) time efficiency.

---

## 🧠 Intuition
For each element in the list, we compute the **complement** (i.e., `target - num`). If this complement has already been seen in a previous iteration, then we have found our pair. This removes the need for nested loops and allows us to maintain linear complexity.

---

## 🛠️ Approach

- Initialize an empty dictionary `seen` to track each number's index.
- Iterate over the list:
  - For each `num`, calculate its `complement`.
  - Check if the complement exists in `seen`:
    - ✅ Yes → Return the stored index of the complement and current index.
    - ❌ No → Store the current number with its index in `seen`.

---

## 📈 Complexity

| Metric | Value     |
|--------|-----------|
| Time   | O(n)      |
| Space  | O(n)      |

`n` is the number of elements in the input array `nums`.

---

## 💻 Code Snippet

```python
class Solution(object):
    def twoSum(self, nums, target):
        seen = {}
        for i, num in enumerate(nums):
            complement = target - num
            if complement in seen:
                return [seen[complement], i]
            seen[num] = i
