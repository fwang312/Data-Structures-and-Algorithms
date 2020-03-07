## Leetcode 680. Valid Palindrome II

Given a non-empty string s, you may delete at most one character. Judge whether you can make it a palindrome.

```html
Example1:
Input: "aba"
Output: True

Example2:
Input: "abca"
Output: True
Explanation: You could delete the character 'c'.
```

```html
class Solution:
    def validPalindrome(self, s: str) -> bool:
        l = 0
        r = len(s) - 1
        while l < r:
            if s[l]  == s[r]:
                l += 1
                r -= 1
            else:
                return s[l:r] == s[l:r][::-1] or s[l+1:r+1] == s[l+1:r+1][::-1]
        return True
                
```
* As usual, initial the left as the first position and the left as the last position.

* If the left and right are the same, then we increase right by one and decrease left by one.

* Then we continue to check the characters between them, if they are not palindrome then we will try to delete the left character or right characters and check the rest is palindrome or not.

* else checks after delete right/left character and see if they satisfy the palindrome or not.
