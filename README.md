# 实现功能
1. 十进制数的简单方法计算：加、减、乘、除等
2. 科学计算函数：三角函数(`sin`,`cos`,`tan`,`ctan`)、指数、开方等函数运算；
3. 判断输入的格式是否正确；
# 设计思想
根据用户从键盘输入的表达示，为实现功能需要完成以下任务
1. 判断表达示是否合法；
2. 取得表达示的操作符与操作数；
3. 判断操作符的优先级并根据优先级依次计算
## 总体流程图
![](index_files/c33b81f9-0462-4818-9164-7abf6a4a8ff2.png)

# 详细设计
## 表达式是否符合规范要求
进行表达式合法性检测时，括号的匹配检测是最重要，需要对表达式从左往右依次扫描，并将左括号进行保存，而遇到右括号里需要与最一个保存的左括号匹配
## 计算表达式
1. 首先要取得表达式中不同的运算元素，对其进行优先级排序，将优先级高的高的先进行运算；
2. 后面运算符优先级依次变高时，需要将前面的运算符保存，直到没有优先级更高的操作符连续出现时，将从后往前对保存的运算符进行运算；
3. 由于上述操作都需要保存一些数据，且是后保存的先进行计算，这里使用栈（后进先出），存储数据可以数组或链表。一般用 Push()和Pop()来插入和删除元素，也称为入栈和出栈。
4. 计算三角等函数需要用 `math.h`头文件
## 函数设计