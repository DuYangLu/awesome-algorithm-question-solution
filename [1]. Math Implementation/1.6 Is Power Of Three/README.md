# Is Power Of Three（是否是3的幂）





## From

[LeetCode 326](https://leetcode.com/problems/power-of-three/description/)





## Question

Given an integer, write a function to determine if it is a power of three.

**Follow up:**
Could you do it without using any loop / recursion?




## Solution  



### Swift

```swift
class Solution {
    func isPowerOfThree(_ num: Int) -> Bool {
        var num = num
        if(num > 1){
            while(num % 3 == 0){
                num = num / 3;
            }
        }

        return num == 1
    }

    func isPowerOfThree_2(_ num: Int) -> Bool {
        // Int 范围内最大的 3 的幂一定能整除所有 3 的幂
        return num > 0 && (Int(pow(Double(3),Double(19))) % num == 0)
    }
}

var s = Solution()
var result = s.isPowerOfThree(81)
print(result)

var result2 = s.isPowerOfThree_2(81)
print(result2)
```

