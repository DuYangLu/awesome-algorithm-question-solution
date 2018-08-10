# Is Power Of Two （是否是2的幂）



## From 

 [LeetCode 231](https://leetcode.com/problems/power-of-two/description/)



## Question

Given an integer, write a function to determine if it is a power of two.




## Solution  



### Swfit

```swift
class Solution {
    func isPowerOfTwo(_ num: Int) -> Bool {
        let max = Int(log2(Double(Int.max))) - 1
        let maxResult = Int(pow(Double(2), Double(max)))
        return num > 0 && (maxResult % num == 0)
    }

    func isPowerOfTwo_2(_ num: Int) -> Bool {
        if (num == 1){
            return true
        }
        if (num >= 2 && num % 2 == 0){
            return isPowerOfTwo(num / 2)
        }
        return false
    }
}


var s = Solution()
var result = s.isPowerOfTwo(8)
print(result)

var result2 = s.isPowerOfTwo_2(8)
print(result2)
```

