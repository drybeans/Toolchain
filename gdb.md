####命令概览
```
- g++ -g test.cpp //生成带调试信息的a.out文件
- gdb a.out       //开始调试a.out
- l               //列出部分源码
- 直接回车        //重复上一次命令
- b 16            //在行16设置断点
- b func          //在函数func设置断点
- r               //开始运行程序
- n               //单条语句执行，不进入函数体
- s               //单条语句执行，进入函数体
- u               //运行程序，直到退出循环体
- c               //继续运行程序
- p i             //打印变量i的值
- bt              //查看函数堆栈
- finish          //退出函数
- c               //继续运行程序
- q               //退出gdb
```

####程序运行参数
- set args 可指定运行时参数（如set args 10 20 30 40 50）
- show args 命令可以查看设置好的运行参数

####调试已运行的程序，两种方法：
- 在Unix下用ps查看正在运行的程序的PID（进程ID），然后用gdb \<program\> PID格式挂接正在运行的程序
- 先用gdb \<program\> 关联上源代码，并进行gdb，在gdb中用attach命令来挂接进程的PID，并用detach来取消挂接的进程

####设置断点
- break \<function\>
- break \<linenum\>
- break +offset
- break -offset
- break filename:linenum
- break filename:function
- break *address //在程序运行的内存地址处停住
- break //表示在下一条指令出挺住
- break ... if \<condition\>
- info breakpoints [n]

####设置观察点
- watch \<expr\>
- rwatch \<expr\>
- awatch \<expr\>
- info watchpoints

####设置捕捉点
- catch \<event\>
> event可以是：throw[一个C++抛出的异常]，catch[一个C++捕捉到的异常]

####维护停止点
- clear
- delete
- disable
- enable

####停止条件维护
- condition \<bnum\> \<expression\>
- condition \<bnum\> //清楚断点号为bnum的停止条件
- ignore \<bnum\> \<count\> //忽略断点号为bnum的停止条件count次

####为停止点设置运行命令
```
commands [bnum]
...command list...
end
```

####信号
- info handle/signals
- handle \<signal\> \<keywords...\>

> signal: SIGINT/SIGBUS/SIGCHILD/SIGKILL... keywords: nostop/stop/noprint/print/pass...

####线程
- break \<linespec\> thread \<threadno\>
- break \<linespec\> thread \<threadno\> if ...
- info threads //查看正在运行的线程信息

####查看堆栈
- info args
- info locals
- info catch

####查看运行时数据
- print \<expr\>
- print /\<f\> \<expr\>

> - @  例如：p *array@len 打印整个数组数据
- :: 例如：p 'f2.c'::x 打印f2.c文件中x变量的值
- \<f\>为输出格式：
  - x 十六进制
  - d 十进制
  - u 十六进制显示无符号整形
  - o 八进制
  - t 二进制
  - a 十六进制
  - c 字符
  - f 浮点数格式
