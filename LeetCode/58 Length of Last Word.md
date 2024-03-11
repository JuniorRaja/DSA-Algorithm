# 58. Length of Last Word

Created: March 11, 2024 7:35 AM
Course: LeetCode
Level: Easy

# QUESTION

Given a string `s` consisting of words and spaces, return *the length of the **last** word in the string.*

A **word** is a maximal substring consisting of non-space characters only.

**Example 1:**

```
Example 1:

Input: s = "Hello World"
Output: 5
Explanation: The last word is "World" with length 5.
```

**Example 2:**

```
Input: s = "   fly me   to   the moon  "
Output: 4
Explanation: The last word is "moon" with length 4.
```

# OBSERVATION

- Since length of last word is required, loop from the end

# APPROACH

- 

# SOLUTION

- loop from the end the given string and decrement the pointer. check for non space characters and increment the length variable to get the length of the last word

```csharp
//CODE
public class Solution {
    public int LengthOfLastWord(string s) {            
      int strLen = 0;
      int i = s.Length - 1;

     while (i >= 0 && s[i] == ' ') {i--;};
     while (i >= 0 && s[i] != ' ') {
         strLen++;
         i--;
     }
     return strLen;
    }
}
```