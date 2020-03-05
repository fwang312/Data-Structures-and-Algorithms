## 167. Two Sum II - Input array is sorted

https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/

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
