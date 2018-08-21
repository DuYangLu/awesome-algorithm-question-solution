# Reverse Linked List（反转链表）



## From

[LeetCode 206](https://leetcode.com/problems/reverse-linked-list/description/)



## Question

Reverse a singly linked list.

```
input: 1->2->3->4->5->NULL
output: 5->4->3->2->1->NULL
```

## Solution  

### Swift

```swift
public class ListNode {
    public var val: Int
    public var next: ListNode?
    public init(_ val: Int) {
        self.val = val
        self.next = nil
    }
}

class Solution {
    func reverseList(_ head: ListNode?) -> ListNode? {
        var preNode: ListNode? = nil
        var curNode: ListNode? = head

        while (curNode !== nil) {
            let nextNode = curNode!.next

            curNode!.next = preNode
            preNode = curNode
            curNode = nextNode
        }

        return preNode
    }
}
```

