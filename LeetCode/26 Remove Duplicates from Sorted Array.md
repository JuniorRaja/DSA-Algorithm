# 26. Remove Duplicates from Sorted Array

Created: March 5, 2024 8:14 AM
Course: LeetCode
Level: Easy
ID: 16
Last Edited: March 5, 2024 8:49 AM

# Question

Given a sorted array nums, remove the duplicates in-place such that each element appear only once and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

**Example 1:**

```
Input: nums = [1,1,2]
Output: 2, nums = [1,2,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).

```

**Example 2:**

```
Input: nums = [0,0,1,1,1,2,2,3,3,4]
Output: 5, nums = [0,1,2,3,4,_,_,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums being 0, 1, 2, 3, and 4 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

# OBSERVATION

- Sorted Array and only unique elements
- Do not use extra memory
- Can use pointer approach

# SOLUTION

Taking two pointers i & j = 1

looping through the array and comparing index[j] with prev element

if not eq, then move the curr element to the index of J

return the length of new array

```csharp
public class Solution {
    public int RemoveDuplicates(int[] nums) {
        if (nums.Length == 0) {
            return 0;
        }

        int j = 0;
        for (int i = 1; i < nums.Length; i++) {
            if (nums[j] != nums[i]) {
                nums[++j] = nums[i];
            }
        }

        return j + 1;
    }
}
```

```csharp
//Fastest solution - Referred
public class Solution {
    public int RemoveDuplicates(int[] nums) {
    int count = 0;
    foreach (int element in nums) 
				if (element != nums[count]) 
					nums[++count] = element;
    return ++count;
	}
}
```