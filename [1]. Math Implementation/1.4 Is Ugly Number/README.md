# Is Ugly Number （是否是丑数）



## From

[LeetCode 263](https://leetcode.com/problems/ugly-number/description/)





## Question

Write a program to check whether a given number is an ugly number.

Ugly numbers are positive numbers whose prime factors only include `2, 3, 5`. For example, `6, 8` are ugly while `14` is not ugly since it includes another prime factor `7`.

**Note:**

1. `1` is typically treated as an ugly number.
2. Input is within the 32-bit signed integer range.





## Solution  



### Swift

```swift
class Solution {
    func isUgly(_ num: Int) -> Bool {
        if (num == 0) {
            return false
        } else if (num == 1) {
            return true
        } else if num % 2 == 0 {
            return isUgly(num / 2)
        } else if num % 3 == 0 {
            return isUgly(num / 3)
        } else if num % 5 == 0 {
            return isUgly(num / 5)
        } else {
            return false
        }
    }
}
```

