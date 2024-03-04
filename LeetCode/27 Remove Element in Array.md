# 27. Remove Element in Array

Created: March 4, 2024 8:20 AM
Course: LeetCode
Level: Easy
ID: 18
Last Edited: March 4, 2024 8:30 AM

# Question

Given an array nums and a value val, remove all instances of that value in-place and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

The order of elements can be changed. It doesn't matter what you leave beyond the new length.

**Example 1:**

```
Input: nums = [3,2,2,3], val = 3
Output: 2, nums = [2,2,_,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 2.

```

**Example 2:**

```
Input: nums = [0,1,2,2,3,0,4,2], val = 2
Output: 5, nums = [0,1,4,0,3,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums containing 0, 0, 1, 3, and 4.
Note that the five elements can be returned in any order.
```

# APPROACH

Two-pointer approach

# OBSERVATION

- Return the new length.
- Use the same input array. No Extra space
- Order can be changed.

# SOLUTION

Take two pointers i = 0 & j = 0

Let i point to the index where the non-matching value should be stored

Let j be used to loop through the array

Check if the current loop value not equal to given ‘val’, then write that element in the input array at position i

Return the i value as it will hold how many have been replaced (removed)

```csharp
public class Solution {
    public int RemoveElement(int[] nums, int val) {
        byte count = 0;
        for(byte i = 0; i < nums.Length; i++){
            if(!nums[i].Equals(val)){
                nums[count++] = nums[i];
                //count++;
            }
        }
        return count;
    }
}
```