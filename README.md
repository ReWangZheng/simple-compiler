# 简单编译器的实现
### 已实现
- 语法分析
实现了支持自定义文法，程序会自动分析文法，求出First集合、Follow集合并且算出预测分析表。根据预测分析表，我们可以直接写出PDA进行语法分析，因为时间关系，写的比较粗糙，后面如果有时间会对其进行改良

以下为定义的语法

        <开始>:<函数定义>
        <函数定义>:<类型><变量>(<参数声明>) {<函数块>}
        <参数声明>:<声明>|$
        <赋初值>:=<右值>|$
        <右值>:<表达式>
        <表达式>:<因子><项>
        <数字闭包>:<数字><数字闭包>|$
        <因子>:<因式><因式递归>
        <因式递归>:*<因式><因式递归>|/<因式><因式递归>|$
        <因式>:(<表达式>)|<变量>|<数字>
        <数字>:1|2|3|4|5|6|7|8|9|0
        <项>:+<因子><项>|-<因子><项>|$
        <声明>:<类型><变量>
        <类型>:int|void|double|long|short|
        <取地址>:$
        <变量>:<标志符>
        <标志符>:regan|CNN|RNN|main|a|b|c
        <函数块>:<声明语句闭包><函数块闭包>
        <声明语句闭包>:<声明语句><声明语句闭包>|$
        <声明语句>:<声明>;
        <声明>:<类型><变量><赋初值>
        <函数块闭包>:<赋值函数><函数块闭包> |<for循环><函数块闭包>|<条件语句><函数块闭包>|<函数返回><函数块闭包>|$
        <函数返回>:return<因式>;
        <for循环>:for (<赋值函数><逻辑表达式>;<后缀表达式>) {<函数块>}
        <赋值函数>:<变量>=<右值>; 
        <逻辑表达式>:<表达式><逻辑运算符><表达式>
        <逻辑运算符>:=|!=
        <后缀表达式>:<变量><后缀运算符>
        <后缀运算符>:+|-

- 词法分析
    实现了有限状态自动机

### 后续
时间关系，还有好多没实现，后面有空了继续来写

