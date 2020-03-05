## 633. Sum of Square Numbers

Given a non-negative integer c, your task is to decide whether there're two integers a and b such that a2 + b2 = c.

```html
Example1:
Input: 5
Output: True
Explanation: 1 * 1 + 2 * 2 = 5
```

```html
Example2:
Input: 3
Output: False
```

```html
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        left = 0
        right = int(c ** 0.5)
        
        while left <= right:
            curr = left **2 + right **2
            if curr < c:
                left += 1
            elif curr > c:
                right -= 1
            else:
                return True
        return False
```

This question is similar to 167. Two Sum II-Input array is sorted, with only one obvious difference: one is the sum of the target, and the other is the square sum of the target.

In this problem, you can also use double pointers to get two numbers, making the sum of their squares equals the target.
