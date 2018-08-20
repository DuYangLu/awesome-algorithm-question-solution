# Insertion Sort Implementation (插入排序算法实现)



## From

Insertion sort



## Question

Insertion sort implementation



## Solution  



### Swift

```swift
class Solution {
    func insertionSort(_ array: [Int]) -> [Int] {
        var array = array
        for i in 1..<array.count {
            let temp = array[i]
            var j = i - 1
            while (j >= 0) {
                if(array[j] > temp) {
                    array[j + 1] = array[j]
                    array[j] = temp
                    j -= 1
                } else {
                    break
                }
            }
        }
        return array
    }
}

var s = Solution()
var result = s.insertionSort([0, 3, 9, 4, 34, 22, 10])
print(result)
```

