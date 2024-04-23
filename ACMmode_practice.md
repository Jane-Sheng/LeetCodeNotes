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
那么每一行末尾的换行符也会被放进字符串中，导致输出格式出现问题。可以增加一个`.strip()`去掉`'\n'`。

## Input
华为的笔试（ACM模式）模板为：
```python
# 这里 import 可能要用的头文件

def func():
    while True:
        try:
            # 这里写所有的操作，包括输入输出
            a, b = map(int, input().strip().split())
            print(a + b)
        except EOFError:
            break


if __name__ == "__main__":
    func()
```
- `.strip()`用于去除首尾的空格和换行。
- `.split()`按照空格或换行将字符串分开。
- 如果行数已经确定可以不需要。题目明确说明有多少行输入，这样代码里只用读取固定行输入即可。题目没明确说明的，需要判断是否读到EOF，采用`while True:`的循环模式。

## Output
格式化输出：保留指定位数的小数
```python
print('%.4f' % x)
```
