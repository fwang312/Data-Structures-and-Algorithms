## 88. Merge Sorted Array

Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

Note:

- The number of elements initialized in nums1 and nums2 are m and n respectively.
- You may assume that nums1 has enough space (size that is greater or equal to m + n) to hold additional elements from nums2.

```html
Input:
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6],       n = 3

Output: [1,2,2,3,5,6]
```
Solution:
```html
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        while m > 0 and n > 0:
            if nums1[m-1] < nums2[n-1]:
                nums1[m+n-1] = nums2[n-1]
                n = n - 1
            else:
                nums1[m+n-1], nums1[m-1] = nums1[m-1], nums1[m+n-1]
                m = m - 1
        if m == 0 and n > 0:
            nums1[:n] = nums2[:n];
```

Explanation:

- nums1 and nums2 is sorted, this is very helpful for us to merge nums2 to nums1

- Combine from the end is a good choice since the output is sorted and the largest value is one the right side(end)

- While loop use the m and n as index, compare the value of nums1[m-1] and nums2[n-1], need "m -= 1' or 'n -= 1"

- Swap function inside nums1

- For m > n, don't care since it is already sorted

- For n > m, insert all the left part in nums2 into nums1

- Don have to 'return nums1' base on the requirement
