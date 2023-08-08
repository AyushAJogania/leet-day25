# leet-day25

# Search in Rotated Sorted Array - LeetCode Problem

## Problem Statement

You are given an integer array `nums` sorted in ascending order (with distinct values). Prior to being passed to your function, `nums` is possibly rotated at an unknown pivot index `k` (`1 <= k < nums.length`) such that the resulting array is `[nums[k], nums[k+1], ..., nums[n-1], nums[0], nums[1], ..., nums[k-1]]` (0-indexed).

Given the array `nums` after the possible rotation and an integer `target`, return the index of `target` if it is in `nums`, or -1 if it is not in `nums`.

You must write an algorithm with O(log n) runtime complexity.

## Example

**Input:** `nums = [4,5,6,7,0,1,2]`, `target = 0`  
**Output:** `4`

**Input:** `nums = [4,5,6,7,0,1,2]`, `target = 3`  
**Output:** `-1`

**Input:** `nums = [1]`, `target = 0`  
**Output:** `-1`

## Approach

This problem can be solved using a modified binary search approach. The key idea is to determine whether the target lies in the left half or the right half of the rotated array based on the comparison of elements at the mid, left, and right positions.

1. Initialize two pointers `left` and `right` pointing to the start and end of the array.
2. While `left` is less than or equal to `right`, calculate the `mid` index.
3. Compare the `mid` element with the `target` element:
   - If they are equal, return `mid`.
   - If `nums[left] <= nums[mid]`, it means the left half is sorted. Check if the `target` is within the range `[nums[left], nums[mid]]`. If so, update `right = mid - 1`, else update `left = mid + 1`.
   - If `nums[mid] < nums[right]`, it means the right half is sorted. Check if the `target` is within the range `[nums[mid], nums[right]]`. If so, update `left = mid + 1`, else update `right = mid - 1`.

If the target is not found during the search, return `-1`.

## Complexity

- Time complexity: O(log n) - The binary search reduces the search space by half in each iteration.
- Space complexity: O(1) - The algorithm uses a constant amount of extra space for pointers and variables.
