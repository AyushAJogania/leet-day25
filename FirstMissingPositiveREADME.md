# leet-day25

# Smallest Missing Positive Integer Finder

## Description
Given an unsorted integer array `nums`, this algorithm finds the smallest missing positive integer in the array. The algorithm rearranges the array to put every valid positive integer in its correct position, and then finds the first missing positive integer.

## Approach
The algorithm iterates through the array and rearranges it by placing each valid positive integer in its correct position. The correct position for the integer `x` is at index `x - 1` (0-based indexing). This is done by swapping `x` with the element at index `x - 1` until the element at index `x - 1` is already `x`. After rearranging, the algorithm iterates through the array again to find the first index `i` where `nums[i] != i + 1`. The missing positive integer is then `i + 1`.

## Algorithm Steps
1. Iterate through the array to rearrange the elements in their correct positions using the swapping technique.
2. Iterate through the array again to find the first missing positive integer.
3. Return the smallest missing positive integer found in step 2.

## Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(1)

## Example
```cpp
class Solution {
public:
    int firstMissingPositive(vector<int>& nums) {
        int n = nums.size();
        
        // Rearrange the array to put every valid positive integer in its correct position
        for (int i = 0; i < n; i++) {
            while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i]) {
                swap(nums[i], nums[nums[i] - 1]);
            }
        }
        
        // Find the first missing positive integer
        for (int i = 0; i < n; i++) {
            if (nums[i] != i + 1) {
                return i + 1;
            }
        }
        
        return n + 1;
    }
};
