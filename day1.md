# Problem 1: Contains Duplicates
```
Given an array of integers, find if the array contains any duplicates.

Your function should return true if any value appears at least twice in the array,
and it should return false if every element is distinct.
```

## Planning:
```
I know that for this problem I'm going to want to compare the length of the array
by the length of a duplicate restricted data structure such as a set.

so something like
if length(array) > length(set) -> True
else -> False

to save on using a if/else im going to return the result of comparing the lengths
this approach only really works because the function is returning a bool datatype

```

## Problem Results: [Here](https://leetcode.com/submissions/detail/385782884/)

## Input:
```
[1, 2, 3, 1]
```


```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        return len(nums) != len(set(nums))
```

```
Output:
true

Expected:
true
```

# Problem 2: Add Two Numbers (Linked List)

```
You are given two non-empty linked lists representing two non-negative integers.
The digits are stored in reverse order and each of their nodes contain a single digit.
Add the two numbers and return it as a linked list.
You may assume the two numbers do not contain any leading zero, except the number 0 itself.
```
## Planning:

```
You are given two non-empty linked lists representing two non-negative integers.
The digits are stored in reverse order and each of their nodes contains a single digit.
Add the two numbers and return the product as a linked list.
You may assume the two numbers do not contain any leading zero, except the number 0 itself.

there are a lot of things happening here so let's break down.
The first two linked lists with values in reverse order are going to have to be
transversed and the product of each node values is going to have to be stored
as a linked list in the same reverse order.

the arguments of the function suggest to use a recursive method to transverse
the list's to accomplish this I'm going to have to repeat the following steps:
find the product
calc the carry
append a new node to the return list

until the input linked lists are read all the way and the entire output list is
complete, given in the direction there is mention that the number that is given
is not going to be with leading zeros so I'm not going to have to account for
that in the code, however, if one number is sorter the other then I'm going
to want to add trailing zeros to fill in so the computation doesn't end up
with errors for trying to add values to None types.
```

## input:
```
(2 -> 4 -> 3)
(5 -> 6 -> 4)
```

## code:
```python
# Definition for singly-linked list.
class ListNode:
     def __init__(self, val=0, next=None):
         self.val = val
         self.next = next

class Solution:
    def addTwoNumbers(self, l1, l2 ,c = 0):
        # take sum of first node in linked list
        val = l1.val + l2.val + c
        # calculate the carry value
        c = val // 10
        # set return node value to leftover
        ret = ListNode(val % 10 )

        # check if w continue transversal through the linked list
        if (l1.next != None or l2.next != None or c != 0):
            # balance the lists if they are different length
            if l1.next == None:
                l1.next = ListNode(0)
            if l2.next == None:
                l2.next = ListNode(0)
            # apply function on next node in list
            ret.next = self.addTwoNumbers(l1.next,l2.next,c)
        return ret

```

## output:

```
(7 -> 0 -> 8)
```
