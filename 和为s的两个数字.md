[leetcode](https://leetcode-cn.com/problems/he-wei-sde-liang-ge-shu-zi-lcof/)

```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) 
    {
        vector<int> v;
        int begin = 0, end = nums.size()-1;
        while(begin < end)
        {
            int ret = nums[begin] + nums[end];
            if(ret == target)
            {
                v.push_back(nums[begin]);
                v.push_back(nums[end]);
                break;
            }
            if(ret > target)
               --end;
            if(ret < target)
               ++begin;
        }
        return v;
    }
};
```

**解题思路**：双指针+如果和大于目标则--end，反之++begin