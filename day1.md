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

Problem 2: Add Two Numbers (Linked List)

```
input:
(2 -> 4 -> 3)
(5 -> 6 -> 4)
```


```python
# Definition for singly-linked list.
class ListNode:
     def __init__(self, val=0, next=None):
         self.val = val
         self.next = next

class Solution:
    def addTwoNumbers(self, l1, l2 ,c = 0):
        val = l1.val + l2.val + c
        c = val // 10
        ret = ListNode(val % 10 )

        if (l1.next != None or l2.next != None or c != 0):
            if l1.next == None:
                l1.next = ListNode(0)
            if l2.next == None:
                l2.next = ListNode(0)
            ret.next = self.addTwoNumbers(l1.next,l2.next,c)
        return ret

```

```
output:

(7 -> 0 -> 8)
```
