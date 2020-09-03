# C-Note
C语言的边角料问题

### 1.strcpy和lstrcpy的区别

- strcpy是C运行时函数,是标准C提供的函数
- lstrcpy是Windows API
- 而StrCpy仅仅是lstrcpy的调用而已,相当于lstrcpy
- 在微软的开发环境里比方说VC开发windows程序，最好使用lstrcpy()，否则很多地方会出问题，用了lstrcpy()就放心多了 
---
### 2.wsprintf和swprintf的区别

- wsprintf是windows api，不支持浮点输出
- swprintf是c库函数，用法和sprintf一样（格式都一样），只不过针对的是宽字符
``` c
swprintf(FPSString, L"%f", FPS);   //正确
wsprintf(FPSString, L"%f", FPS);   //错误
```
