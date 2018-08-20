# Linked List Cycle (链表是否有环)



## From

 [LeetCode 141](https://leetcode.com/problems/linked-list-cycle/description/)





## Question

Given a linked list, determine if it has a cycle in it.



## Solution 



### Swift

```c++
class ListNode {
    var next: ListNode!
    init() {
    }
    init (next: ListNode) {
        self.next = next
    }
}

class Solution {
    func hasCycle(_ head: ListNode) -> Bool {
        var slowerNode = head
        var fasterNode = head

        while(slowerNode != nil && fasterNode != nil && fasterNode.next != nil){
            slowerNode = slowerNode.next
            fasterNode = fasterNode.next.next

            if(slowerNode === fasterNode){
                return true
            }
        }
        return false
    }
}

var s = Solution()
var n0 = ListNode()
var n1 = ListNode()
var n2 = ListNode()
var n3 = ListNode()
var n4 = ListNode()
n0.next = n1
n1.next = n2
n2.next = n3
n3.next = n4
n4.next = n3
var result = s.hasCycle(n0)
print(result)
```

