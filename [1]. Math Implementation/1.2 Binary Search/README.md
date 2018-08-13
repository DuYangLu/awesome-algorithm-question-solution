# Binary Search （二分查找）



## From

One of common searching algorithm problems



## Question

Binary search implementation.



## Solution  



### Swift

```swift
class Solution {
    func binarySearch(_ array: [Int], _ value: Int) -> Int {
        var left = 0
        var right = array.count - 1

        while (left <= right) {
            let middle = left / 2 + right / 2
            if (array[middle] > value) {
                right = middle - 1
            } else if (array[middle] < value) {
                left = middle + 1
            } else {
                return middle
            }
        }
        return -1
    }
}

var s = Solution()
var result = s.binarySearch([0, 6, 9, 10, 22, 555, 999], 6)
print(result)
```

