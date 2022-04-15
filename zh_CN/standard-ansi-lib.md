#  C(ANSI C)语言标准函数库

### C标准库概述

#### 基本说明
从语言本身的角度(与平台无关)来说，标准C语言（ANSI C）共定义了15 个头文件，截至C11标准共包含29个头文件。

#### 各标准差异：
| 标准名称 | 头文件差异 |
|:-------:|:---------|
| C89  | 15 标准头文件 |
| C90、C89 | 标准头文件无差异, 排版存在差异 |
| C95 | +3 标准头文件 |
| C99 | +6 标准头文件 |
| C11 | +5 标准头文件 |
| C17 | 无 |

### C标准库按使用频度:

常用：

* 一组：
```
stdio.h
ctype.h
stdlib.h
string.h
```

* 二组：
```
assert.h
limits.h
stddef.h
time.h
```

* 三组：
```
float.h
math.h
error.h
locale.h
setjmp.h
signal.h
stdarg.h
```

### 标准库备注

| 头文件 |	标准版本 |	备注|
|:-----:|:-----:|:--------|
| assert.h |	C89/C90 | 条件编译宏，将参数与零比较  |
| ctype.h |	C89/C90 |	用于确定包含字符数据中的类型 |
| errno.h |	C89/C90 |	报告错误条件宏,内含3个宏(EDOM	特定含义的错误，在math.h 中表示域错误;ERANGE	特定含义的错误，在math.h 中表示溢出错误;errno	库函数中用来盛放错误代码的宏) |
| float.h |	C89/C90 |	浮点数类型,提供范围和精度的宏，包含了一组与浮点值相关的依赖于平台的常量 |
| limits.h |	C89/C90 |	检测整型数据数据类型的表达值范围 |
| locale.h |	C89/C90 |	本地化 |
| math.h |	C89/C90 |	常用数学函数库 |
| setjmp.h |	C89/C90 |	非局部跳转 |
| signal.h |	C89/C90 |	信号处理 |
| stdarg.h |	C89/C90 |	可变参数 |
| stddef.h |	C89/C90 |	常用宏定义 |
| stdio.h |	C89/C90 |	输入/输出 |
| stdlib.h |	C89/C90 |	standard library标准库函数库：内存管理、程序工具、字符串转换、随机数 |
| string.h |	C89/C90 |	字符串处理 |
| time.h  |	C89/C90 |	时间处理 |
| wchar.h |	C95 |	扩展多字节和宽字符处理 |
| wctype.h |	C95 |	包含了一系列用于检测和转换单个宽字符的函数库，wctype.h 是ctype.h的宽字符版本，wctype.h的出现晚于ctype.h。wctype.h的引入使C语言可以更好地处理英文以外的语言。 |
| complex.h |	C99 |	复数运算 |
| fenv.h |	C99 |	浮点数环境 |
| inttypes.h | C99 |	整数类型的格式转换 |
| stdbool.h |	C99 |	布尔类型 |
| stdint.h |	C99 |	定宽整数类型 |
| tgmath.h |	C99 |	泛型数学（包装 math.h 和 complex.h 的宏） |
| stdalign.h | C11 |	alignas 与 alignof 便利宏 |
| stdatomic.h | C11 |	原子类型 |
| stdnoreturn.h |	C11 |	noreturn 便利宏 |
| threads.h |	C11 |	线程库 |
| uchar.h |   C11 | UTF-16 和 UTF-32 字符工具 |



### 运行时库

#### C run-time library（CRT）

* C运行时库区别于C++语言的运行时库，指的是C程序运行时需要调用的库的函数，是一个相对概念
* C运行时库由编译器生产商提供，亦称为第三方 C 运行库（Third party C run-time libraries）
* C运行时库一般是平台或系统提供，windows或linux，macos等。



### Universal C Runtime 库（UCRT 库）
通用C运行时库，包含多C库的头文件，Windows组件之一，自win10开始以系统发行方式部分提供。关联库：
* 对应的lib库为libucrt.lib
* 对应的dll库为ucrtbase.dll

UCRT库文件：

| 库 | 关联的DLL | 备注 | 选项 | 预处理器指令 |
|:---:|:---:|:---:|:---:|:---:|
| libucrt.lib |	无 | 将 UCRT 静态链接到你的代码。 |	/MT	| _MT |
| libucrtd.lib | 无 | 用于静态链接的 UCRT 调试版本。不可再发行。 | /MTd |	_DEBUG,_MT |
| ucrt.lib | ucrtbase.dll | UCRT 的 DLL 导入库。  |	/MD |	_MT,_DLL  |
| ucrtd.lib | ucrtbased.dll | UCRT 调试版本的 DLL 导入库。不可再发行。  |	/MDd  | _DEBUG,_MT,_DLL  |


