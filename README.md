# C-Note
C语言的边角料问题

### 1.strcpy 和 lstrcpy 的区别

- strcpy是C运行时函数,是标准C提供的函数
- lstrcpy是Windows API
- 而StrCpy仅仅是lstrcpy的调用而已,相当于lstrcpy
- 在微软的开发环境里比方说VC开发windows程序，最好使用lstrcpy()，否则很多地方会出问题，用了lstrcpy()就放心多了 
---
### 2.wsprintf 和 swprintf 的区别

- wsprintf是windows api，不支持浮点输出
- swprintf是c库函数，用法和sprintf一样（格式都一样），只不过针对的是宽字符
``` c++
swprintf(FPSString, L"%f", FPS);   //正确
wsprintf(FPSString, L"%f", FPS);   //错误
```
---
### 3.wsprintf缓冲区大小为1024字节
---
### 4.delete 和 delete[] 的区别
- delete ptr ：用来释放内存，且只用来释放ptr指向的内存。
- delete[] rg：用来释放rg指向的内存，还逐一调用数组中每个对象的destructor。
- 对于像int/char/long/int*/struct等等简单数据类型，由于对象没有destructor，所以用delete 和 delete[] 是一样的！但是如果是C++对象数组就不同了。
```C
A *a = new A[10];
delete a; //仅释放了a指针指向的全部内存空间 但是只调用了a[0]对象的析构函数 
          //剩下的从a[1]到a[9]这9个用户自行分配的m_cBuffer对应内存空间将不能释放 从而造成内存泄漏
```
---
### 5.ConvertSidToStringSidA 的 StringSid 释放
```C
BOOL ConvertSidToStringSidA(
  PSID  Sid,
  LPSTR *StringSid // To free the returned buffer, call the LocalFree function.
);
```
