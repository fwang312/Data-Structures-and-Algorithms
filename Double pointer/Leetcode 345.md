## 345. Reverse Vowels of a String
Write a function that takes a string as input and reverse only the vowels of a string.

```html
Example:
Input: "leetcode"
Output: "leotcede"
```


```html
class Solution:
    def reverseVowels(self, s: str) -> str:
        vowels = 'aeiou'
        string = list(s)
        i, j = 0, len(s) - 1
        while i < j:
            if string[i].lower() not in vowels:
                i += 1
            elif string[j].lower() not in vowels:
                j -= 1
            else:
                string[i], string[j] = string[j], string[i]
                i += 1
                j -= 1
        return"".join(string)
```

- With double pointers, one pointer traverses from beginning to end and one pointer traverses from end to end.

- When both pointers traverse to the vowel character, the two vowel characters are exchanged.

- To quickly determine if a character is a vowel character, we add all vowel characters to the set "vowels" (like a dictionary)

- The original positions of i and j are 0 and len (s) -1

- The title does not mention capitalization rules, so I converted all of them to lowercase
