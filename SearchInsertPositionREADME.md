# leet-day25

# Binary Search to Find Insertion Position

## Problem Statement

Given a sorted array of distinct integers and a target value, the task is to find the index where the target value should be inserted in order to maintain the array's sorted order. If the target is already present in the array, return its index. This problem can be solved using an algorithm with O(log n) runtime complexity.

## Example

**Input:**
```
nums = [1, 3, 5, 6]
target = 5
```
**Output:**
```
2
```
**Explanation:**
The target value 5 is already present at index 2 in the array.

## Approach

The approach involves utilizing binary search to find the target value or its appropriate insertion position. The algorithm maintains two pointers, `left` and `right`, which define the current search range. In each iteration, the algorithm calculates the middle index (`mid`) of the search range and compares the value at index `mid` with the target value.

- If the value at index `mid` is equal to the target value, the algorithm returns the index `mid`.
- If the value at index `mid` is less than the target value, the algorithm updates the `left` pointer to `mid + 1` to search the right half of the array.
- If the value at index `mid` is greater than the target value, the algorithm updates the `right` pointer to `mid - 1` to search the left half of the array.

If the target value is not found after the binary search, the `left` pointer indicates the correct insertion position for the target value.

## Complexity Analysis

- Time Complexity: The binary search approach has a time complexity of O(log n), where n is the number of elements in the array.
- Space Complexity: The algorithm uses constant extra space, resulting in a space complexity of O(1).

This solution provides an efficient and optimal way to find the insertion position for a target value in a sorted array, ensuring that the runtime complexity remains O(log n).
