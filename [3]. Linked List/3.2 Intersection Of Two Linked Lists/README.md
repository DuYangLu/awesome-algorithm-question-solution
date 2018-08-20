# Intersection Of Two Linked Lists (两个链表是否有交点)



## From 

[LeetCode 160](https://leetcode.com/problems/intersection-of-two-linked-lists/description/)





## Question


编写一个程序，找到两个单链表相交的起始节点。

例如，下面的两个链表：

```
A:          a1 → a2
                   ↘
                     c1 → c2 → c3
                   ↗            
B:     b1 → b2 → b3
```

在节点 c1 开始相交。

注意：

如果两个链表没有交点，返回 null.
在返回结果后，两个链表仍须保持原有的结构。
可假定整个链表结构中没有循环。
程序尽量满足 O(n) 时间复杂度，且仅用 O(1) 内存。

## Solution  



### Python

```python
class ListNode(object):
    def __init__(self, val):
        self.val = val
        self.next = None

class Solution(object):
    def getIntersectionNode(self, headA, headB):
        if headA is None or headB is None:
            return None

        headALen = self.getCount(headA)
        headBLen = self.getCount(headB)

        if headALen < headBLen:
            result = headBLen - headALen
            while result > 0:
                result -= 1
                headB = headB.next

        if headALen > headBLen:
            result = headALen - headBLen
            while result > 0:
                result -= 1
                headA = headA.next

        ha = headA
        hb = headB

        temp = None
        while ha is not None and hb is not None:
            if ha == hb:
                temp = ha
                break
            else:
                ha = ha.next
                hb = hb.next
            
        return temp

    def getCount(self, listNode):
        i = 1
        node = listNode
        while node.next is not None:
            i += 1
            node = node.next
        return i
        

s = Solution()
c1 = ListNode('c1')
c2 = ListNode('c2')
c3 = ListNode('c3')
c1.next = c2
c2.next = c3

a1 = ListNode('a1')
a2 = ListNode('a2')
a1.next = a2
a2.next = c1

b1 = ListNode('b1')
b2 = ListNode('b2')
b3 = ListNode('b3')
b1.next = b2
b2.next = b3
b3.next = c1

result = s.getIntersectionNode(a1, b1)
print(result.val)
        
```

