# Bubble Sort Implementation (冒泡排序算法实现)



## From

Bubble sort



## Question

Bubble sort implementation



## Solution  



### Swift

```swift
class Solution {
    func bubbleSort(_ array: [Int]) -> [Int] {
        var array = array
        for i in 0..<array.count - 1 {
            for j in 0..<array.count - 1 - i {
                if (array[j] > array[j + 1]){
                    let temp = array[j]
                    array[j] = array[j + 1]
                    array[j + 1] = temp
                }
            }
        }
        return array
    }
}

var s = Solution()
var result = s.bubbleSort([0, 3, 9, 4, 34, 22, 10])
print(result)
```

