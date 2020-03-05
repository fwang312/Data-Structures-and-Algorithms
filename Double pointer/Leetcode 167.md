## 167. Two Sum II - Input array is sorted(easy)

https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/
```html
Input: numbers={2, 7, 11, 15}, target=9
Output: index1=1, index2=2
```

```html
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
    
        start = 0
        end = len(numbers) -1
        sum = 0
    
        while start != end:
            sum = numbers[start] + numbers[end]
            if sum > target:
                end -= 1
            elif sum < target:
                start += 1
            else:
                return [start+1, end+1]
```

We use the double pointers here, one pointer to the element with large values and other one with the small values, pointers point to the small element start from the beginning to end and the ohter one start from the end to the beginning.

- If the sum of the two pointers elements = target then is what we need

- If the sum < target, move the small pointer to the right to make the sum larger.

- If the sum > target, move the large pointer to the left to make the sum smaller.

We use the 0 as the base index rather than 1 so we need to +1 when we output the actual value.

Time:O(N), Space:O(1)
