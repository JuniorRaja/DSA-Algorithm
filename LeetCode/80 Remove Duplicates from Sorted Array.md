# 80. Remove Duplicates from Sorted Array II

Created: March 3, 2024 2:22 PM
Class: LeetCode
Level: Easy
ID: 16
Last Edited: March 3, 2024 2:55 PM

# Question

Given a sorted array nums, remove the duplicates in-place such that duplicates appeared at most twice and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

**Example 1:**

```
Input: nums = [1,1,1,2,2,3]
Output: 5, nums = [1,1,2,2,3,_]
Explanation: Your function should return k = 5, with the first five elements of nums being 1, 1, 2, 2 and 3 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).

```

**Example 2:**

```
Input: nums = [0,0,1,1,1,1,2,3,3]
Output: 7, nums = [0,0,1,1,2,3,3,_,_]
Explanation: Your function should return k = 7, with the first seven elements of nums being 0, 0, 1, 1, 2, 3 and 3 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

# OBSERVATION

- Can allow two duplicates
- Do not use extra memory
- Can use pointer approach to

# SOLUTION

Since the first two elements of the array will be in the A. Ascending Order B. Can allow two duplicates. So, starting to loop nums[ ] from the index 2.

Taking the 3rd position as index, comparing if the element already exists with the previous element

If the number does not exists already, we replace in the existing array

return the length of the new array through the index

```csharp
public class Solution {
    public int RemoveDuplicates(int[] nums) {
        if(nums.Length < 3) return nums.Length;
        int idx = 2;
        for(int i = 2; i < nums.Length; i++){
            if(nums[idx-2] != nums[i]){
                nums[idx++] = nums[i];
            }
        }
        return idx;
    }
}
```

```csharp
//Fastest solution - Referred
public class Solution {
    public int RemoveDuplicates(int[] nums) {
        int total = nums.Length;

        for(int i=2; i<nums.Length; i++){
            if(nums[i]==nums[i-1]&&nums[i]==nums[i-2]){
                nums[i] = nums.Max()+1;
                total--;
                i--;
            }
            Array.Sort(nums);
        }
        return(total);
    }
}
```