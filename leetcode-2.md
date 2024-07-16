name: "Add Two Numbers"
link: "https://leetcode.com/problems/add-two-numbers/"

```go
/*
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func addTwoNumbers(l1 *ListNode, l2 *ListNode) *ListNode {
    
    head := new(ListNode)
    iterator := head

    carry := 0

    for l1 != nil && l2 != nil {

        sum := l1.Val + l2.Val + carry

        if sum>9 {
            carry = 1
        } else {
            carry = 0
        }

        sum %= 10

        temp := &ListNode {
            Val: sum,
        }

        iterator.Next = temp
        iterator = iterator.Next

        l1 = l1.Next
        l2 = l2.Next
    }

    for l1 != nil {
        sum := l1.Val + carry

        if sum>9 {
            carry = 1
        } else {
            carry = 0
        }

        sum %= 10

        temp := &ListNode {
            Val: sum,
        }
        
        iterator.Next = temp
        iterator = iterator.Next

        l1 = l1.Next
    }

    for l2 != nil {
        sum := l2.Val + carry

        if sum>9 {
            carry = 1
        } else {
            carry = 0
        }

        sum %= 10

        temp := &ListNode {
            Val: sum,
        }
        
        iterator.Next = temp
        iterator = iterator.Next

        l2 = l2.Next
    }

    if carry>0 {
        temp := &ListNode {
            Val: carry,
        }
        
        iterator.Next = temp
    }

    return head.Next

}
```
