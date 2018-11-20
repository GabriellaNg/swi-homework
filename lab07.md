# 硬件编程–机器指令编程
## 任务一：简单编程
**（1）打开网页 The PIPPIN User’s Guide ，然后输入 Program 1：Add 2 number  
（2）点step after step。观察并回答下面问题：**  
1.PC：程序计数器，指示指令在储存器中的地址。完成一条指令后会自动递增，指向下一条指令。  
IR：指令寄存器。解析和存放当时正在进行的指令。  
2.ACC：累加寄存器，用来存储ALU的计算结果。  
3.通过LOD指令获取数值3——>寄存于IR中——>通过Decoder对指令LOD解析——>3通过MUX，ALU存于ACC中  
![](images/4.png)
4.获取指令ADD W存于IR中——>通过Decoder解析ADD——>通过MUX获取W——>获取ACC中的数据——>在ALU中计算W和ACC中的数据并存于ACC中  
![](images/5.png)
5.ADD W比LOD #3中多一个获取数据的步骤  
**（3）点击“Binary”,观察回答下面问题**  
000|1|0100|00000111
-|-|-|-
前导0|寻址模式（数值）|操作码|代表数值7
![](images/6.png)
2.RAM用于储存操作指令  
3.16位
```
int x=3,y=7;
int z=x+y
printf("%d",z);
```
# 任务二：简单循环
1.x=3,x每循环一次减一，直到x=0跳出循环  
```
int x=3
while(x>0)
{
    x--;
}
```
(2)  
1.
```
int x=10,y=0;
while(x>0)
{
    y=y+x;
    x--;
}
```
|0|LOD X|
|-|-|
|2|SUB #1|
4|JMZ 14
6|STO X
8|ADD Y
10|STO Y
12|JMP 0
14|HLT
X|11
Y|0
3.机器语言和高级语言原理是一样的，但高级语言使用更方便，高级语言的运行要转化为机器语言。