# Array/String
## 1768. Merge Strings Alternately
python字符串`str`和数组相关函数
- 字符串长度：`len(str)`
- 字符串中单个字符调用：`str[i]`
- 数组创建：`result = []`
- 数组添加：`result.append(str[i])`
- 数组转字符串：`''.join(result)`

思路：利用`while`和`if`嵌套，`i`表示`word1`和`word2`中的第`i`个字符

## 1071. Greatest Common Divisor of Strings
字符串最大公因数算法
- 字符串有最大公因数的充要条件是`str1 + str2 == str2 + str1`
- 输出`str1`的前最大公因数个字符切片就行

str相关函数
- 可直接相加：`str1 + str2` 用`=`判断是否完全相同
- 前n个字符的切片：`str[:n]`
- 空字符串：`""`

最大公因数`gcd`函数
- 调用最大公因数函数
```python
from math import gcd
gcd(m,n)
```

## 1431. Kids With the Greatest Number of Candies
简单题

注意`result = []`数组添加需要用`.append()`

## 605. Can Place Flowers
可以改变`flowerbed`数组

直接判断前后和本身是否为0

注意特例：两端可以种花 当`i == 0`和`i == len() - 1`时要加“或”的判断

## 345. Reverse Vowels of a String
注意`str`不能直接进行`=`赋值操作，要先复制一个`list`格式的：`word = list(s)`

最后把它变成`str`返回：`return "".join(word)`

str查找
- 先定义要找的字符串：`vowels = "aeiouAEIOU"`
- 再把查找的判断语句写成：`vowels.find(word[i])`  如果找不到会返回`-1`，如果找到会返回开始的下标

## 151. Reverse Words in a String
数组的切片是数组，不能直接切片

思路
- 不要用双指针手写
- python `split`再`reverse`可以一行搞定

str相关函数
- 分割：`str.split(str="", num=string.count(str))` 按`str`分割，分成`num`个，输出是数组（[参考网址](https://www.runoob.com/python/att-string-split.html"https://www.runoob.com/python/att-string-split.html") ）
- 反转：`reversed`(任意迭代器)可以倒过来

## 238. Product of Array Except Self
思路：创建`prefix`和`suffix`存储向前和向后的数的积

## 334. Increasing Triplet Subsequence
特殊算法：和`first` `second`比大小。比`first`小成为`first`，比`first`大但比`second`小成为`second`，比`first`和`second`都大就`true`。

## 443. String Compression
双指针问题，注意理清`if` `while` `for`嵌套思路

# Two Pointers
## 283. Move Zeroes
双指针简单题

## 392. Is Subsequence
简单题

## 11. Container With Most Water
注意优化思想：更低的一边需要优化

不是特别理解，有时间理解一下为什么这样一定能找到最优解

## 1679. Max Number of K-Sum Pairs
先排序后双指针

O(1)的方法是用哈希来做，以后研究一下

# Sliding Window
## 643. Maximum Average Subarray I
把平均数转化成和，求最大和只需要重新计算变化的首尾两个数

## 1456. Maximum Number of Vowels in a Substring of Given Length
字符串查找
```python
vowel = 'aeiou'
if str[i] in vowels:
```
enumerate()
```python
>>> for i, element in enumerate(seq):
...     print i, element
...
```
```
0 one
1 two
2 three
```

## 1004. Max Consecutive Ones III
一种window的特殊解法：

双指针代表窗口左右坐标，`k`相当于窗口内0的个数，`k`为正时可以向右拉长，新数字为1可以向右拉长，`k`为负时，如果窗口左边第一位是0那么向右移动并`k`加一，如果是1那么向右移动`k`不变。

## 1493. Longest Subarray of 1's After Deleting One Element
继续用上一题的解法
也可以储存每个连续1的长度，比较得出最大值

# Prefix Sum
## 1732. Find the Highest Altitude
简单题

## 724. Find Pivot Index
`range(1,1)`为空

倒序`range(n-1, -1, -1)`

善用`sum()`

# Hash Map / Set
## 2215. Find the Difference of Two Arrays
使用`set()`可转换数组删掉重复，`A - B`可以从`A`中删掉`B`中出现的元素，再转回数组就行

for特别用法：
```python
first = [n for n in set(nums1) if n not in nums2]
```

## 1207. Unique Number of Occurrences
先排序，然后遍历，得到出现次数，出现次数排序。最后检查出现次数有无重复。

排序：`arr.sort()`

## 1657. Determine if Two Strings Are Close
充要条件：出现的字母频率`sort`以后应该是相同的

用`[0] * 26`来记录每个`word`中26个字母出现的频率

`ord(ch)`表示字符`ch`的ascii码

## 2352. Equal Row and Column Pairs
哈希
- `Counter()`调用方法同字典
- 二维`list`转换成转置元组列表`zip(*grid)`
- 二维`list`转换成元组列表`map(tuple,grid)`

# Stack
## 2390. Removing Stars From a String
对字符串(str)`s`可以用`for`遍历 `for i in s`

数组形式的栈：
- 出栈：`stack.pop()`
- 入栈：`stack += i`

## 735. Asteroid Collision
没什么好说的，就是用栈(FILO)

用`while`和`i`来控制变量，可以调整`i`怎么变，比`for`灵活

## 394. Decode String
Medium题，感觉比较难。

注意出栈入栈的顺序。用`curnum`存目前在`[`前面的数字，用`curstr`存解码后的字符串。每次遇到`[`就将`curnum`和`curstr`入栈备用，遇到了`]`就`pop`两次得到前缀`prevstr`和目前要对`curstr`重复的次数`prevnum`，组合成新的`curstr`。每次遇到字符直接加在`curstr`后面。最后`curstr`就是解码得到的字符串。

因为`[` `]`能保证成对出现，所以每次遇到`[`就入栈暂存数字和前缀，`]`出栈两次把目前的字符串组合完成，能保证`[` `]`操作匹配。

# Queue
## 933. Number of Recent Calls
双端队列`deque` (`collections`库)
- 用数组实现的
- 头文件
  ```python
  import collections
  ```
- 创建
  ```python
  queue =collections.deque()
  ```
- 入列单个
  ```python
  queue.append('s')
  queue.appendleft('a')
  ```
- 入列多个（注意加在`left`是倒过来的顺序）
  ```python  
  queue.extend(['a', 'b'])
  queue.extendleft(['a', 'b'])
  ```
- 出列
  ```python
  queue.popleft()
  queue.pop()
  ```
## 649. Dota2 Senate
中等题，感觉代码写得不错所以写了个[solution](https://leetcode.com/problems/dota2-senate/solutions/5058067/python3-simple-solution-beats-95"python3-simple-solution-beats-95")

比较关键的想法是用两个队列存储两个队的下标，每次比较队首下标，大的删除，小的**加n**加到队尾。

# Linked List
## 2095. Delete the Middle Node of a Linked List
python单链表包括`node.val`和`node.next`

可以直接`node.next.next = node.next`来删除`node`后一个节点

## 328. Odd Even Linked List
简单，理清链表连接顺序防止调用错误就行。注意`node==None`是特例，需要另外判断。

## 206. Reverse Linked List
基础题，注意`cur`，`prev`和`next`存储三个前后节点，给`head`添加前置节点`prev`。关注的是中间的节点。

两行就能写完：
```python
while curr:       
		curr.next, prev, curr = prev, curr, curr.next
```
最后倒置过的链表表头是`prev`

## 2130. Maximum Twin Sum of a Linked List
暴力求解是遍历节点把`val`存成数组，求`max`。空间复杂度O(n)。

更符合题意的做法是快慢指针找中点，把后半部分倒置（方法同上一道题），然后两个指针同时往后移求`max`。

注意一些细节和逻辑。

# Binary Tree-DFS
## 104. Maximum Depth of Binary Tree
递归调用

定义`dfs(node,depth)`

## 872. Leaf-Similar Trees
使用递归，在递归函数当中判断是否是叶节点

## 1448. Count Good Nodes in Binary Tree
DFS:
- 不能把节点个数放在外面统计，每次让递归函数让它+1，因为没法在递归函数中调用这个全局变量。（试了`global`也不可以）。
- 看到了一个`solution`在`solve()`函数中先调用子节点的自身，获得当前子树的`good`点的个数，再判断自身是否是`good`点，再向上传递当前`good`点个数。但是它的时间复杂度很高以至于只打败了15%……

BFS:
用队列`deque()`存储节点地址和当前最大值，使用BFS遍历整个二叉树并且统计当前的`good`点个数。看起来可行并且高效的。

## 437. Path Sum III
字典调用
```python
dict.get(key, value)
```
如果该键值不存在，会返回`None`或者指定的`value`，而一般用`dict[key]`调用时，如果`key`不存在会报错。

时间、空间复杂度O(n)，主要思路：对每个节点递归调用DFS，用字典`cache`记录当前节点所在的整条路径上路径长度`currPathSum`与出现的次数。目标`targetSum`视作`currPathSum`与`oldSum`的差，因此只要查找当前的`cache`中`oldSum`出现的频次加到`result`。

几个易错点：
- 由于每条不同的路径上`cache`都不同，需要及时清除和修改，字典`cache`作为参数传递到`dfs`函数里面。而result是“全局”变量，用`self.result`。
- `targetSum = oldSum + currPathSum`，计算`oldSum`的时候不要弄错了。
- 为了避免调用不存在的键值导致报错，修改字典时不应该用`cache[currSum] += 1`，要用`cache[currSum] = cache.get(currSum, 0) + 1`。
- 每当一个root节点左右子节点都被遍历过了，这条路径之后就不能再被算进任何一条`oldSum`里去，所以要将字典中此路径和`currPathSum`的出现频率-1。

## 1372. Longest ZigZag Path in a Binary Tree

# Binary-BFS
## 199. Binary Tree Right Side View
递归调用

定义`bfs(node, lvl)` 判断条件：若`lvl=res[]`就加当前值

# Binary Search Tree
## 700. Search in a Binary Search Tree
递归调用的时候需要`return`

调用自己这个类函数需要`self.function()` 如果不是类里的不需要`self.`

# Graphs-DFS
## 841. Keys and Rooms
用了队列`deque()`以及`popleft()` DFS

一个集合`set()`表示访问过的房间，一个队列表示要搜索房间的队列

# Graphs-BFS
## 1926. Nearest Exit from Entrance in Maze
`node`只存同一距离的不重复的合理的未检查过是否是边界的节点，`for in range(len(node))`当这一距离的`node`全部检查并且后一距离的合理节点入队列过后，`step`+1，来记录步数。
