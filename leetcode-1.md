name: "Two Sum"
link: "https://leetcode.com/problems/two-sum/"

```go
func twoSum(nums []int, target int) []int {

    // make a hashmap (num:index)
    hashMap := make(map[int] int)

    var ans []int // array to store the answer

    for idx, num := range nums {
        if existingIdx, ok := hashMap[target-num]; ok {
            ans = append(ans, idx, existingIdx)
            break
        }

        hashMap[num] = idx
    }

    return ans
}
```
