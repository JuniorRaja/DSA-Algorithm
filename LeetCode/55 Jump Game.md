# 55. Jump Game

Created: March 8, 2024 8:37 AM
Course: LeetCode
Level: Medium

# QUESTION

You are given an integer array `nums`. You are initially positioned at the array's **first index**, and each element in the array represents your maximum jump length at that position.

Return `true` *if you can reach the last index, or* `false` *otherwise*.

**Example 1:**

```
Input: nums = [2,3,1,1,4]
Output: true
Explanation: Jump 1 step from index 0 to 1, then 3 steps to the last index.
```

**Example 2:**

```
Input: nums = [3,2,1,0,4]
Output: false
Explanation: You will always arrive at index 3 no matter what. Its maximum jump length is 0, which makes it impossible to reach the last index.
```

# APPROACH

- Two pointers

# SOLUTION

- Working backwards on the array
- If the nearest true is 0 then the whole array is jumpable

```csharp
//CODE
public class Solution {
    public bool CanJump(int[] nums) {
        int nearestTrue = nums.Length - 1;

        for(int i = nums.Length - 2; i>= 0 && nearestTrue > i; i--){
            if(i + nums[i] >= nearestTrue){
                nearestTrue = i;
            }
        }

        return nearestTrue == 0;
    }
}
```