#  C Macro 宏


# 定义
#define 宏定义命令，C语言预处理命令。标识符来表示一个字符串，代码运行中会将表示符进行全部替换成指定的字符串。

```
#define N 1
int main(){
    int sum = 1 + N;
    printf("Output: %d\n", sum);
    return 0;
}
// output: 2
```
# 宏定义和定义全局变量的区别和注意事项

* 作用时间不同：宏定义在编译期间即会使用并替换，而全局变量要到运行时才可以。 
* 本质类型不同：
    * 宏定义的只是一段字符，在编译的时候被替换到引用的位置。
      在运行中是没有宏定义的概念的。而变量在运行时要为其分配内存。 
    * 宏定义不可以被赋值，即其值一旦定义不可修改，而变量在运行过程中可以被修改。
* 宏定义只有在定义所在文件，或引用所在文件的其它文件中使用。
全局变量可以在工程所有文件中使用，只需在使用前加一个声明就可以，即宏定义不支持extern模式。



