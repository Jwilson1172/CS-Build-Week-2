<p>leet code challenges</p>

# Two Sums:
## results page:

<a href='https://leetcode.com/submissions/detail/386299516/'>Results</a>

## code :
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        q = {}
        for idx,val in enumerate(nums):
            product = target - val
            if product not in q:
                q[val] = idx
            else:
                return [q[product], idx]
```

## status:
```
passing all test cases
```

<br>
<br>
<br>
<br>

# Implementing a Queue
## Results Page:

<a href='https://leetcode.com/submissions/detail/386297719/'>Results</a>

## Code:
```python
class MyQueue:

    def __init__(self):
        """
        Initialize your data structure here.
        """
        self.q = []
        self.len = 0
        return
    def __str__(self):
        return str(self.q)

    def push(self, x: int) -> None:
        """
        Push element x to the back of queue.
        """
        self.q.append(x)
        self.len += 1
        return None

    def pop(self) -> int:
        """
        Removes the element from in front of queue and returns that element.
        """
        self.len -= 1
        return self.q.pop(0)


    def peek(self) -> int:
        """
        Get the front element.
        """
        return self.q[0]


    def empty(self) -> bool:
        """
        Returns whether the queue is empty.
        """
        return self.len == 0
```

## Status:
```
passing all testcases
```
