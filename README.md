# 为了luceda波导设计开始学python（理论）

2022/1/13

## 基本知识
### 注释 

```
单行注释： #

多行注释： ctrl + '\'> 
```

  ### 变量命名规则

```
组成：大小写字母+数字+下划线

多单词变量名：第一个单词首字母小写、后面单词首字母大写

大小写要区分
```

### 赋值语句

```
a=b=c=10 # 10的值赋给a,b,c
a,b,c = c,a,b # c,a,b赋值给a,b,c 
```

### 字符串初步

1.  可以且==必须==用单引号、双引号、三引号括起来
print('she say:"hello."')
print("hello”)
2.  分行书写方法
print("fen \
hang \
shuxie.")
3.  字符串中不能包含变量
4.  ==三双引==号字符串中可包含换行、制表以及其他特殊字符
5.  下标（编号）==从左到右:0,1,2,...
      从右到左:-1,-2,-3,...
      (普遍规律)==
    a = "ABCD", 则a[0]="A", a[-1] = "D"
6.  连接：a = a + b, a = a + b[0]
7.  字符串中的字符不可直接修改
   错误 a[1] = 'b'
8.  ==in 和 not in 判断是否为子串 （也适用于list）==
    a = "hello"
	b = "python"
    print("el" in a)  #>>Ture
9.  s="a";print(a * 3) #>>aaa,字符串的乘法
9. 字符串切片s[x:y]，从下标x到下标y，x算在内，y不算在内



## 字符串与数的转换

+ int(x) : 把字符串转换为整数
+ float(x): 字符串转换为小数
+ str(x): x转换为字符串
+ eval(x): 字符串x的内容，看成一个python表达式，求其值
+ int("a12")、int（"1.2"）、float("abc")均为不合法转换>>runtime error
+ int（1.2）#1, 合法取整

```python 
a = 15;b = "12";
c = a + b; #False 字符串与数不能相加
c = a + int(b) #>>27
c = str(a) + b #>>"1512"
c = eval("3+2")#>>5
c = eval("3+a")#>>18
c = eval("3+b")#>>False 字符串与数不能相加
c = eval("3+int(b)")>>18,数 
c = eval("3"+b)>>312，数
c= 3 + eval(a)#>>18
```

## 数据类型

+ int 
+ float
+ str
+ bool
+ tuple 元组
+ dict 字典
+ set 集合
+ complex 
+ list 列表

## 输出、输入==(返回为字符串类型)==

```Python
print(1,2,3,end="");
print("ok")
>>1 2 3ok #不换行 
a = int(input("提示信息： "));
b = int(input());#每次输入一行，多行用多次input

#格式控制
#attention!!格式控制符只能出现在字符串中
%s #表示此处输出一个字符串
%d #表示此处输出一个整数
%f #表示此处输出一个小数
%.nf #表示此处输出一个n位小数,4舍6入，5可舍可入
h = 1.746
print("My name is %s,I am %.2fm tall." % ("lihua",1.746))

#格式控制不一定用在输出中
s = input().split()
x,y = float(s[0]),float(s[1])
m = '%.5f' % (x+y) #不一定用在输出中
```

## list、列表、[]

从0到任意多元素，可用下标访问

```
empty = [];#空白表
list1 = ['a', 'b',1,2];
print(list1[0]);#>>a
list1[1] = 'c';#更改列表元素
a = 1;
print("更新后第二个元素为：", list1[a]);#变量也可作为下标
print(1 in list1);#True
```

## 字符串到列表

```
s = input()
list1 = s.split() # 空格、制表符\t、换行符\n
a = int(list1[0]) + int(list1[1])
输入：3 4
则 s = ["3 4"]
list1 = ["3","4"]
>> a=7
```

==练习==

```
#字符三角形
s = input()
print("  "+s)
print(" "+s*3)
print(s * 5)
>> 
  *
 ***
*****

#(a+b)*c
s = input().split()
a,b,c = int(s[0]),int(s[1]),int(s[2])
print((a+b)*c)

#反向输出三位数
n = input()
print(n(2)+n(1)+n(0))

#加减乘除简单计算器
s = input().split()
if s[2] not in ["+","-","*","/"]:
	print("Invalid operator!")
elif s[2] == "/" and int(s[1])==0:
	print("Divided by zero!")
else:
	print(int(eval(s[0] + s[1] + s[2])) #int此处为取整作用 
```

## 算术运算

加减乘除==小数==（/）、求商==正负都往小取整==(//）、取模 or 取余（%）、求幂（**）

+ 有小数参加的表达式，结果一定是小数
+ 3+-5=-2
+ /哪怕算出的是整数，算出的结果也为小数
+ a+=3 # a=a+3，其他运算同

## 关系运算符结果为bool类型（True(1)\False(0)）

+ ==
+ !=
+ <>
+ \>=  \<=
+ 字符串的关系运算符为对应的ascii码值的关系运算

## 逻辑运算符

and or not

优先级：算术运算符>关系运算符>not>and>or

##  相当于True和False

+ 1、非空字符串和列表都相当于True，但只有1==True
+ 0、空字符串""、空列表[]等都相当于False，但只有0==False

## 条件分支语句

```python
if <statement1>:
	<statement2>
elif<statement3>:
	<statement4>
...
else:
	<statement5>
	
```

==Python程序的语句前面不能加空格或者制表符，除非==

+ 在if、for、while语句的某个语句组中，必须缩进并且缩进的情况必须一样
+ 函数体中

## for循环语句

```python
for i in range(5): #[0,5)
    print(i)
for i in range(5,9):#[5,9)
    print(i)
for i in range(0,10,3):#3表示步长
	print(i)
    
#for 循环遍历列表写法一
a = ["huawei","goole","baidu"]
for i in range(len(a)):#len可用来求字符串、列表、元组、集合、字典元素个数
    print(i,a[i])
>>
1 huawei
2 goole
3 baidu

# for 循环遍历列表写法二
a = ["huawei","goole","baidu"]
for i in a:
    print(i)
>>
huawei
goole
baidu

# for 循环遍历字符串
for letter in "abc":
	print(letter)
>>
a
b
c

#连续输出26个字母
for i in range(26):
    print(chr(ord("a")+i),end="")
```

### break 和 continue

```python
sites = ["Baidu","Goole","IBM","ali"]
for site in sites:
    if site == "IBM"
    	print("OK")
     print("site: "+site)
else:
    print("No break")
print("done")
>>
site: Baidu
site: Goole
OK
site: IBM
site: ali
No break
done

#break
sites = ["Baidu","Goole","IBM","ali"]
for site in sites:
    if site == "IBM"
    	print("OK")
        break
     print("site: "+site)
else:
    print("No break")
print("done")
>>
site: Baidu
site: Goole
OK
done

#Continue
for letter in "TAOBAO":
    if letter == "o":
        continue
    print(letter)
>>
T
A
B
A
```

## for循环简单练习

```python
#从大到小输出整数n的因子
n = int(input())
for i in range(n,0,-1):
	if n % i == 0:
    	print(i," ",end="")

#多重循环
for i in range(m)
	...
    for j in range(n)
    	...
        #执行n×m次的循环

```

## While

```python
while <>:
    <>
else:
    <>
    
#例子1
while(input("请输入密码：") != "sjtu"):
    print("密码错误")
print("密码输入成功")
>>
请输入密码：stju
密码错误
请输入密码：SJTU
密码错误
请输入密码：sjtu
密码输入成功

#求输入3个整数的最小公倍数
s = input().split()
a,b,c = int(s[0]),int(s[1]),int(s[2])
m = n =max(a,b,c)
while(n % a or n % b or n % c != 0):
    n+=m
print(n)
```

## 循环综合练习

```python
#求斐波那契数列的第k项
k = int(input())
a1=a2=1;
if k==1 or k==2:
    print(1)
else
	for i in range(k-2)
		a1,a2=a2,a1+a2
    print(a2)

#求阶乘的和
n = int(input())
s = 0
for i in range(1,n+1):
    f = 1
    for j in range(1,i+1):
        f *= j
     s += f
print(s)

#求阶乘的和
n = int(input())
s,f = 0,1
for i in range(1,n+1):
    f *= i
    s += f
print(s)

#求不大于整数n的全部质数（除了1和自身没其他因数,1不是质数）
n = int(input())
print(2)
ok = True
for i in range(3,n+1,2):#偶数肯定不是质数，只判断奇数
    for j in range(3,i,2):#奇数肯定没有2这个因子
        if i%j==0:
            ok = False
            break
        if j*j>i:#大于根号i的数可以不用试
            break
if ok
	print(i)
```



## 异常处理

try:

​	<statement1>

except:

​	<statement2>

如果在<statement1>中出现了异常，从<statement1>中跳出，执行<statement2>

常见的异常有：

- 不合适的转换，如int("a")

- 输入已经结束，还在执行input
- 除数为0
- 整数和字符串相加
- 列表下标越界

```python
#输入若干行，每行若干整数，求所有整数最大值
s = input()
lst = s.split()
maxV = int(lst[0])
try:
    while True
    	lst = s.split()
        for x in lst:
            maxV = max(int(x),maxV)
        s = input()
except:
    pass
print(maxV)
```



### 注

- 程序顶格书写









