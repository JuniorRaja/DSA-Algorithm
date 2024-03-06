# 169. Majority Element

Created: March 5, 2024 9:10 PM
Course: LeetCode
Level: Easy
ID: 19
Last Edited: March 5, 2024 9:14 PM

# Question

Given an array `nums` of size `n`, return *the majority element*.

The majority element is the element that appears more than `⌊n / 2⌋` times. You may assume that the majority element always exists in the array.

**Example 1:**

```
Input: nums = [3,2,3]
Output: 3

```

**Example 2:**

```
Input: nums = [2,2,1,1,1,2,2]
Output: 2
```

# APPROACH

- Moore's Voting Algorithm

# SOLUTION

Use Moore’s Voting Algorith to find the candidate and allocate points as we iterate through the array

```csharp
public class Solution {
    public int MajorityElement(int[] nums) {
        int points = 0;
        int candidate = 0;

        foreach(int num in nums){
            if(points == 0){ candidate = num; }
            points += (candidate == num) ? 1 : -1;
        }
        return candidate;
    }
}
```