Problem 1: Contains Duplicates

<a href="https://leetcode.com/submissions/detail/385782884/">Results</a>


```
Input:
[1, 2, 3, 1]
```


```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:

        # case : All elements are unique
        if len(set(nums)) == len(nums):
            return False

        # case : there are duplicate values in array
        if len(set(nums)) < len(nums):
            return True
```

```
Output:
true

Expected:
true
```

Problem 2: Two Sums

