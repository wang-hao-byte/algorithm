[leetcode](https://leetcode-cn.com/problems/remove-nth-node-from-end-of-list/)

```
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) 
    {
        ListNode* slow = head,*quick = head;
        while(n--)
        {
            quick = quick->next;
        }
        if(quick == NULL)
        {
            return head->next;
        }
        while(quick->next)
        {
            slow = slow->next;
            quick = quick->next;
        }
        ListNode* tmp = slow->next;
        slow->next = tmp->next;
        return head;
    }
};
```

**解题思路**：快慢指针，但是需要注意当quick为空的情况；