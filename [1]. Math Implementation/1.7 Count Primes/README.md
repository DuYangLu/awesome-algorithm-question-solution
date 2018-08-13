# Count Primes （质数的个数）



## From

[LeetCode 204](https://leetcode.com/problems/count-primes/description/)





## Question

Count the number of prime numbers less than a non-negative number, **n**.

**Example:**

```
Input: 10
Output: 4
Explanation: There are 4 prime numbers less than 10, they are 2, 3, 5, 7.
```

## Solution  



### Swift

```swift
class Solution {
    func countPrimes(_ n: Int) -> Int {
        if n <= 2 {
            return 0
        }
        if n < 4 {
            return 1
        }
        if n == 4 {
            return 2
        }
        let sqr: Int = Int(sqrt(Double(n)))

        var set: Set<Int> = Set()
        for i in 2..<n {
            set.insert(i)
        }
        for i in 2...sqr {
            if (isPrime(i)) {
                var coefficient = 2
                var temp = i * coefficient
                while temp < n {
                    set.remove(temp)
                    coefficient += 1
                    temp = i * coefficient
                }
            }
        }
        return set.count
    }

    func isPrime(_ num: Int) -> Bool {
        let tmp = num;
        for i in 2..<tmp {
            if(num % i == 0){
                return false
            }
        }
        return true
    }
}
```

