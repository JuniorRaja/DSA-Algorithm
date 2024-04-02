# 14. Longest Common Prefix

Created: March 11, 2024 7:50 AM
Course: LeetCode
Level: Easy

# QUESTION

- Write a function to find the longest common prefix string amongst an array of strings. If there is no common prefix, return an empty string `""`.

**Example 1:**

```
Input: strs = ["flower","flow","flight"]
Output: "fl"
```

**Example 2:**

```
Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```

# OBSERVATION

- 

# APPROACH

- 

# SOLUTION

- Sort the array in asc order of the length of each string
- Pick the shortest and longest string and compare their charAt
- Return the matching length of strings
- Make sure that do not go out of bounds

```csharp
//CODE

public class Solution {
    public string LongestCommonPrefix(string[] strs) {
        
        Array.Sort(strs, (x, y) => x.Length.CompareTo(y.Length));
        string str1 = strs[0];
        string str2 = strs[strs.Length - 1];
        int idx = 0;

        while(idx <= str1.Length){
            if(str1[idx] == str2[idx]){
                idx++;
            }
            else {
                break;
            }
        }
        return idx == 0 ? "" : str1.Substring(0, idx);
    }
}
```