# Array / String
## 122. Best Time to Buy and Sell Stock
Kadane's Algorithm: 一种更新`max_cur`和`max_global`的算法。

只要遍历一遍数组，记录当前的买入点`buy`和最高利润`profit`，如果当前数字比买入点更低，更新买入点；如果当前数字和买入点之间的差值比最高利润更大，更新`profit`。如此，最后保存的利润就是最高的利润。

