
## **一.C++的四个语言子集，四种语言风格**
```
1.c_like
2.Object_Oriented C++
3.Template C++
4.STL
```
## **二.宁可以编译器替换与处理器**
```
 原因是，预处器会将#define处理定义的符号替换为具体的值，报错出现的也是具体的值，如果这个值不是你自己写的，那么很难知道其含义，与出处。出现了问题，增加处理成本。
    多使用 const，enum，inline替换#define
    使用常量可以比#define有更少的编码，预处理器的替换，会在每一处都替换，而编译器使用的是符号表。
    对于指针，两个const修饰的指针才有#define的效果。
    string对象通常比char* 更合宜。
    class常量，用static成员，static const type varName;
在声明时获得初值，在定义时不必再赋初值。
    
    如果你不想让别人的某个指针或引用指向你的某个整数常量，enum可以帮助你实现这个约束。
    对于形似函数的宏，最好用inline函数替换#defines。
```

## **三.尽可能用const**
```
    const可以修饰global或namespace作用域中的常量，或可以修
饰文件、函数、或区块作用域中被声明为static的对象。也可以修饰成员变量。可以修饰指针的指向与指向的值。
    声明迭代器为const，类似声明一个T* const 指针。
    const_iterator,STL模拟一个const T* 指针。
    用const创建常量对象，const Type var;
    真实的程序中const对象多用于passed by pointer-to-const
或 passed by referenct-to-const的传递结果。
    函数类型也可以重载，const与non-const？

    当const和non-const成员函数有着实质等价的实现时，
令non-const版本调用const版本可避免代码重复。

```