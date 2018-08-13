# Fibonacci （斐波那契数列实现）



## From

《剑指offer》Question No.9



## Question

Code implementation of fibonacci.



## Solution  



### Swift

```Swift
class Solution {
    // 动态规划
    func fibonacci(_ num: Int) -> Int {
        if (num <= 0) {
            return 0
        }
        if (num == 1) {
            return 1
        }
        return fibonacci(num - 1) + fibonacci(num - 2)
    }
}

var s = Solution()
var result = s.fibonacci(5)
print(result)
```

