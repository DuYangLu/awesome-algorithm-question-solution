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
        var head = head
        var newHead: ListNode? = nil

        while (head !== nil) {
            let nextNode = head?.next

            head?.next = newHead
            newHead = head
            head = nextNode
        }
        return newHead
    }
}

// 以下测试代码

func printNodes(_ head: ListNode?) {
    var head = head
    while (head !== nil) {
        print(head?.val)
        head = head?.next
    }
}

var s = Solution()
var n0 = ListNode(0)
var n1 = ListNode(1)
var n2 = ListNode(2)
var n3 = ListNode(3)
var n4 = ListNode(4)
var n5 = ListNode(5)
n0.next = n1
n1.next = n2
n2.next = n3
n3.next = n4
n4.next = n5

var result = s.reverseList(n0)

printNodes(result)
```

