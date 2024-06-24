# 392. Is Subsequence

Created: June 24, 2024 8:20 AM
Course: LeetCode

# QUESTION

Given two strings `s` and `t`, return `true` *if* `s` *is a **subsequence** of* `t`*, or* `false` *otherwise*.

A **subsequence** of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., `"ace"` is a subsequence of `"abcde"` while `"aec"` is not).

**Example 1:**

```
Input: s = "abc", t = "ahbgdc"
Output: true
```

**Example 2:**

```
Input: s = "axc", t = "ahbgdc"
Output: false
```

# OBSERVATION

- check if the given chars exists in the given string

# APPROACH

- Two pointers

# SOLUTION

- using a pointer for the subseq string
- iterate the string with comparison to the value at the pointer
- return the pointer if the pointer val = subseq string length

```csharp
//CODE

public class Solution {
    public bool IsSubsequence(string s, string t) {
        if(s == "")
            return true;
        int idx = 0;
        for(int i = 0; i < t.Length && idx < s.Length; i++)
            if(t[i] == s[idx])
                ++idx;
        return idx == s.Length;
    }
}
```