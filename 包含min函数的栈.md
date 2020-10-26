[leetcode](https://leetcode-cn.com/problems/bao-han-minhan-shu-de-zhan-lcof/submissions/)

```c++
class MinStack {
public:
    /** initialize your data structure here. */
    stack<int> pushst;
    stack<int> minst;
    MinStack() 
    {}
    
    void push(int x) {
        pushst.push(x);
        if(minst.empty())
        {
            minst.push(x);
        }
        else
        {
            if(minst.top() > x)
              minst.push(x);
            else
              minst.push(minst.top());
        }
    }
    
    void pop() {
        pushst.pop();
        minst.pop();
    }
    
    int top() {
        return pushst.top();
    }
    
    int min() {
        return minst.top();
    }
};

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack* obj = new MinStack();
 * obj->push(x);
 * obj->pop();
 * int param_3 = obj->top();
 * int param_4 = obj->min();
 */
```

**解题思路**：两个栈实现，一个栈永远存储最小值的元素；