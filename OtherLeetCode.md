时间比较紧张，跟着《代码随想录》挑着刷了一部分。

这里仅仅是为了复习用的个人笔记，主要记解题思路，有涉及到摘录的地方侵删。

# 数组
## 二分查找
## 704. Binary Search
注意`left`，`right`指代的查找区间。如果是闭区间`[left, right]`，那么使用`while left <= right` `mid = right - 1` `mid = left + 1`。如果是左闭右开`[left, right)`，那么使用`while left < right` `right = mid` `left = mid + 1`。

细节优化：防止数字溢出，将`mid = (left + right) // 2` 改成 `mid = left + (right - left) // 2`

## 移除元素
## 27. Remove Element
快慢指针法解题，很简单。

## 有序数组的平方
## 977. Squares of a Sorted Array
简单题。时间复杂度O(n)，空间复杂度O(n)的解法是双指针，依次比较左右两端数组的绝对值，由大到小从右到左写入新建的空数组中。

## 长度最小的子数组
## 209. Minimum Size Subarray Sum

# 回溯
## 77. Combination
回溯基本套路（参考自代码随想录）
```python
主函数调用backtracking
def backtracking(参数) 
    if 终止条件:
        存放结果
        return

    for 选择：本层集合中元素（树中节点孩子的数量就是集合的大小）:
        处理节点
        backtracking(路径，选择列表) # 递归
        回溯，撤销处理结果
```

# 贪心算法
## 455. Assign Cookies
分饼干，降序排序孩子和饼干，从大到小每次都试图把最大饼干分给胃口最大的小朋友，如果不能满足那么分给胃口更小的小朋友。这样能尽量多地分配掉。

实现方面，采用了双指针+`while`，只要一层循环且时间复杂度`O(n)`。

# 动态规划
动态规划和贪心算法的区别是：贪心算法从局部最优得到全局最优，而动态规划涉及状态递推，需要根据上一个的状态来决定当前状态。

动态规划五部曲：
> 确定dp数组（dp table）以及下标的含义
>
> 确定递推公式
> 
> dp数组如何初始化
> 
> 确定遍历顺序
> 
> 举例推导dp数组
