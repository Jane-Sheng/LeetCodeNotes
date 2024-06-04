# Array / String
## 121. Best Time to Buy and Sell Stock
Kadane's Algorithm: 一种更新`max_cur`和`max_global`的算法。

只要遍历一遍数组，记录当前的买入点`buy`和最高利润`profit`，如果当前数字比买入点更低，更新买入点；如果当前数字和买入点之间的差值比最高利润更大，更新`profit`。如此，最后保存的利润就是最高的利润。

## 122. Best Time to Buy and Sell Stock II
Medium

本题可以有不限次数的买入和抛出，当天买入抛出和不操作的利润是一样的，因此只要遇到好价就可以买卖，所以可以使用贪心算法。

贪心算法：遍历数组，记录买入点`buy`和总收益`result`，每当当前数字比`buy`更高就抛售一次，增加`result`值，再以当前点为新的买入点；如果当前数字比`buy`更低，也以当前点为新的买入点。这样就能保证收益最高。

