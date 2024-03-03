# 88. Merge Sorted Array

Created: March 3, 2024 3:09 PM
Class: LeetCode
Level: Easy
ID: 16
Last Edited: March 3, 2024 3:29 PM

# Question

Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

Note:

- The number of elements initialized in nums1 and nums2 are m and n respectively.
- You may assume that nums1 has enough space (size that is greater or equal to m + n) to hold additional elements from nums2.

**Example 1:**

```
Input: nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
Output: [1,2,2,3,5,6]
Explanation: The arrays we are merging are [1,2,3] and [2,5,6].
The result of the merge is [1,2,2,3,5,6] with the underlined elements coming from nums1.

```

**Example 2:**

```
Input: nums1 = [1], m = 1, nums2 = [], n = 0
Output: [1]
Explanation: The arrays we are merging are [1] and [].
The result of the merge is [1].

```

**Example 3:**

```
Input: nums1 = [0], m = 0, nums2 = [1], n = 1
Output: [1]
Explanation: The arrays we are merging are [] and [1].
The result of the merge is [1].
Note that because m = 0, there are no elements in nums1. The 0 is only there to ensure the merge result can fit in nums1.
```

# APPROACH

1. Copy second array into first and then perform sort (0(K*log*K) and O(1))
2. Two-pointer approach

# OBSERVATION

- Array is sorted
- Merge second array into first

# SOLUTION

Use two pointers which should be the array length -1

take the length of the merged array ( m + n ) 

Compare two pointers

if p2>p1 then write p2 at the index i

if p2<p1 then write p1 at the index i

```csharp
public class Solution {
    public void Merge(int[] nums1, int m, int[] nums2, int n) {
        int p1 = m-1, p2 = n-1, i = m+n-1;

        while(p2 >= 0){
            if(p1 >=0 && nums1[p1] > nums2[p2]){
                nums1[i--] = nums1[p1--];
            }
            else {
                nums1[i--] = nums2[p2--];
            }
        }
    }
}
```

```csharp
//Fastest solution - Referred
public class Solution {
    public void Merge(int[] nums1, int m, int[] nums2, int n) {
    int index1 = m - 1; // Last index of the first part of nums1
    int index2 = n - 1; // Last index of nums2
    int mergeIndex = m + n - 1; // Last index of merged nums1

    // Merge in reverse order
    while (index2 >= 0) {
        if (index1 >= 0 && nums1[index1] > nums2[index2]) {
            nums1[mergeIndex] = nums1[index1];
            index1--;
        } else {
            nums1[mergeIndex] = nums2[index2];
            index2--;
        }
        mergeIndex--;
    }
}
}
```