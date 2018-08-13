# Is Prime （是否是质数）



## From

Math problem



## Question

To prove if the given number is prime.



## Solution  



### Code

```swift
import Foundation

class Solution {
    func isPrime_1(_ num: Int) -> Bool {
        let tmp = num;
        for i in 2..<tmp {
            if(num % i == 0){
                return false
            }
        }
        return true
    }

    func isPrime_2(_ num: Int) -> Bool {
        let tmp: Int = Int(sqrt(Double(num)))

        for i in 2...tmp {
            if(num % i == 0){
                return false
            }
        }
        return true
    }
}

var s = Solution()
var result = s.isPrime_1(10)
print(result)

var result2 = s.isPrime_2(10)
print(result2)

```

