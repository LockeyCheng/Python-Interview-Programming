### 题目要求

    按行读取一个文件并且输出到标准输出

**分析**

    1、使用文件的open()函数
    2、使用with上下文管理
    按行读取函数readline()的使用

方法一：使用with上下文管理

```python
def read_file_by_line_with(filename):
    with open(filename)  as fo:
        while True:
            line = fo.readline()
            if not line:
                break
            if line == '':
                continue
            print line
```

方法二：使用文件操作的open()函数

```python
def read_file_by_line0(filename):
    fo = open(filename):
    while True:
        line = fo.readline()
        if not line:
            break
        print line
    fo.close()

#如果说文件不是很大的话那么我们就一次性读取然后一行行的输出

def read_file_by_line1(filename):
    fo = open(filename)
    for line in fo:
        print line
```