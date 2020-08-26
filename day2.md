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

## planning:

```
I've done an implementation of a Queue for school because it is not natively
supported datastructure so I'll be using a list for the implementation
this is going to be an O(n)
```


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
# Other Practice

## Problem: running sum of a 1d array

```
```

## planning:

```
this is pretty simple im going to want to iterate through the list taking the sum
fof the array up until that point, iterating through the entire length of the array
for this I went about two ways one by just iterating through the list then taking
the sum with a list comprehension up until point i in the list of nums
the second method that i would use is to use the list slicing syntax of python
to return the sum of the list of nums up until point i in nums eg nums[:i]

```

## code:
```python

class Solution:
    def firstpass(self, nums: List[int]) -> List[int]:
        # init the return list
        ret = []
        # set my loop index to 1
        i = 1
        # iterate the list appending the sum of the running list to the ret
        while i < len(nums) + 1:
            ret.append(sum([nums[x] for x in range(i)]))
            # increment the counter
            i += 1
        # return value
        return ret
    # I belive the first pass solution is O(n*log(n))
    # because for each list that is mad the nex list is 1 shorter of a sequence

    def runningSum(self, nums: List[int]) -> List[int]:
        # this solution uses list compehesion and list slicing to achive the same effect
        # however runtime in this instance should be O(n) because there is
        # no iteration through the list the second time
        return [sum(nums[:i+1]) for i in range(len(nums))]
```


## HackerRank Python & Sql
## Profile Link [Here](https://www.hackerrank.com/JWilson1172)

<a href='sql_README.md'>SQL PROBLEMS</a>

