# GDB调试
## GDB功能
1. 启动程序，可以按照自定义要求运行程序
2. 可以指定断点
3. 当程序被停住，可以检查此时程序所发生的事
4. 可以改变程序，将一个BUG产生的影响修正从而测试其他BUG

## GDB使用
### 启动
gcc -o test.c test -g
gdb test

### 给程序设置参数
set args 
show args

### GDB使用帮助
help

### 查看当前文件代码
- list\l 查看默认行代码
- list\l 行号 : 从指定行显示
- list\l 函数 : 从指定函数显示

### 查看非当前文件代码
- list\l 文件名:行号
- list\l 文件名:函数名

### 设置显示的行数
show list/listsize
set list/listsize 行数

### 设置断点
b\break 行号\函数名\文件名:行号\文件名:函数

### 查看断点
i/info b/break

### 删除断点

d/del/delete 断点编号

### 设置断点无效
dis/disable 断点编号

### 生效断点
ena/enable 断点编号

### 设置条件断点（一般用在循环位置）
b/break 10 if i==5

### 运行GDB程序
start 程序停在第一行
run 遇到断点才停

### 继续运行
c/continue

### 执行下一行代码
n/next

### 变量操作
p/print 变量名(打印变量值)
ptype 变量名(打印变量类型)

### 向下单步调试
s/step
finish(跳出函数体)

### 自动变量操作
display num(自动打印指定变量的值)
i/info display
undisplay 编号

### 其他操作
set var 变量名=变量值
until (跳出循环)