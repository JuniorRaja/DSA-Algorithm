# 28. Find the Index of the First Occurrence in a String

Created: June 21, 2024 6:39 AM
Course: LeetCode

# QUESTION

- Given two strings `needle` and `haystack`, return the index of the first occurrence of `needle` in `haystack`, or `-1` if `needle` is not part of `haystack`.

**Example 1:**

```
Input: haystack = "sadbutsad", needle = "sad"
Output: 0
Explanation: "sad" occurs at index 0 and 6.
The first occurrence is at index 0, so we return 0.
```

**Example 2:**

```
Input: haystack = "leetcode", needle = "leeto"
Output: -1
Explanation: "leeto" did not occur in "leetcode", so we return -1.
```

# OBSERVATION

- Iterate and compare the needle while looping though the haystack

# APPROACH

- 

# SOLUTION

- Check if the needle length is 0
- Iterate through the haystack minus the length of the needle
- compare and if not matching, break the inner loop
- compare and matches, return the index of haystack

```csharp
//CODE
public class Solution {
    public int StrStr(string haystack, string needle) {
        if(needle.Length == 0)
            return -1;

        for(int i = 0; i < (haystack.Length + 1) - needle.Length; i++){

            for(int j=0; j< needle.Length; j++){

                if(haystack[i+j] != needle[j])
                    break;
                if(j == needle.Length -1)
                    return i;
            }
        }
        return -1;
    }
}
```

```csharp
//CODE
public class Solution {
    public int StrStr(string haystack, string needle) {
        var length= needle.Length;
        for (int i = 0; i < haystack.Length - length +1; i++)
        {
            if (haystack.Substring(i, length) == needle)
            {
                return i;
            }
        }
        return -1;
    }
}
```