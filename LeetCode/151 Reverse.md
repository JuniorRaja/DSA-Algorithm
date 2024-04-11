# 151. Reverse

Created: April 3, 2024 8:46 AM
Course: LeetCode
Level: Medium

# QUESTION

- Given an input string, reverse the string word by word.

**Example 1:**

```
Input: s = "the sky is blue"
Output: "blue is sky the"
```

**Example 2:**

```
Input: s = "  hello world  "
Output: "world hello"
Explanation: Your reversed string should not contain leading or trailing spaces.
```

# OBSERVATION

- Possibility of multiple spaces in between words
- Reverse the words with only one space btwn them

# APPROACH

- 

# SOLUTION

- Split the input string with whitespace delimitter
- Iterate through the split array in reverse
- Check if the current word is not a empty string and append to the result
- Adding a blank space after each word
- Finally, remove the last whitespace

```csharp
//CODE

public class Solution {
    public string ReverseWords(string s) {
        string[] strList = s.Split(' ');
        StringBuilder sBuilder = new StringBuilder();

        for(int i = strList.Length - 1; i >=0 ; i-- ){
            if(strList[i].Length > 0) {
                sBuilder.Append(strList[i]);
                sBuilder.Append(" ");
            }
        }

        if(sBuilder.Length > 0)
            sBuilder.Remove(sBuilder.Length-1, 1);

        return sBuilder.ToString();
    }
}
```

```csharp
//CODE Referred
public class Solution
{
    public string ReverseWords(string s) => 
		string.Join(' ', s.Split(' ').Reverse().Where(e => e.Length > 0));
}
```