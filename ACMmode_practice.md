# ACM input and output practice
题库来自 [newcoder.com](https://www.nowcoder.com/exam/test/27976983/summary)

## Example 1
输入：每行两个数字`a` `b`，有任意多行。

输出：两个数字之和`a+b`。
```python
import sys

for line in sys.stdin:
    a = line.split()
    print(int(a[0]) + int(a[1]))
```

## Example 2
```python
n = int(input())
for i in range(n):
    a = list(map(int, input().split(" ")))
    print(sum(a))
```

## Example 3
我自己的
```python
import sys

for line in sys.stdin:
    a = list(map(int, line.split(" ")))
    if not a[0] and not a[1]:
        break
    print(a[0]+a[1])
```
别人的
```python
while True:
    a = list(map(int, input().split(" ")))
    if a[0] == 0 and a[1] == 0:
        break
    else:
        print(sum(a))
```

## Example 10
```python
while True:
    try:
        a = sorted(list(input().split(',')))
        print(','.join(a))
    except:
        break
```
注意，如果还使用
```python
import sys

for line in sys.stdin:
    a = list(line.split(','))
```
那么每一行末尾的换行符也会被放进字符串中，导致输出格式出现问题。因此，当隔开输入的字符不是默认的“空格或者换行符”时，最好不要用`sys`库制造麻烦了。
