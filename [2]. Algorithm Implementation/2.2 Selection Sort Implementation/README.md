# Selection Sort Implementation (选择排序算法实现)



## From 

Selection sort



## Question

Selection sort implementation



## Solution  



### Swift

```swift
class Solution {
    func selectionSort(_ array: [Int]) -> [Int] {
        var array = array
        for i in 0..<array.count {
            var min = i
            for j in i + 1..<array.count {
                if (array[min] > array[j]){
                    min = j;
                }
            }
            if (min != i){
                let temp = array[i]
                array[i] = array[min]
                array[min] = temp
            }
        }
        return array
    }
}

var s = Solution()
var result = s.selectionSort([0, 3, 9, 4, 34, 22, 10])
print(result)
```

