# C-Note
C语言的边角料问题

### strcpy和lstrcpy有什么区别

- strcpy是C运行时函数,是标准C提供的函数
- lstrcpy是Windows API
- 而StrCpy仅仅是lstrcpy的调用而已,相当于lstrcpy
- 在微软的开发环境里比方说VC开发windows程序，最好使用lstrcpy()，否则很多地方会出问题，用了lstrcpy()就放心多了 
