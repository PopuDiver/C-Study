# #  C#_Study

## Lesson1_输入输出

```c#
using System;

namespace Lesson1_输入输出
{
    class Program
    {
        static void Main(string[] args)
        {
            //输出 向控制台打印信息
            //Console.WriteLine("*****");（自动换行）
            //Console.Write("***");

            //输入 向控制台输入内容
            //Console.ReadKey();检测到按键就会结束输入
            //Console.ReadLine();检测到回车才会结束
            Console.WriteLine("Hello World!");
            Console.ReadKey();
        }
    }
}
```

## Lesson2_变量

```c#
using System;

namespace Lesson2_变量
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("变量");

            //知识点一 折叠代码
            //由 #region #endregion配对出现
            //作用 将代码包裹，避免凌乱
            //本质是编辑器提供的预处理指令
            //只在编辑时有用 执行时会被自动删除
            #region 知识点二 如何声明变量

            //变量声明方法
            //变量类型 变量名 = 初始值;
            //虽然C#命名可以使用中文，但是尽量不要使用中文命名
            //变量类型 有14种

            //通过加号来进行拼接打印
            Console.WriteLine("sdsds" + 3);

            //1.有符号的整型 能存储 一定范围 正负数包括0的变量类型
            // sbyte -128 - 127
            // int -21亿 - 21亿
            // short -32768 - 32767
            // long -9百万兆 - 9百万兆

            //2.无符号的整型 能存储一定范围内0和正数的变量类型
            // byte 0 - 255
            // uint 0 - 42亿多的一个范围
            // ushort 0 - 65535之间的一个数
            // ulong 0 - 18百万兆之间的一个数

            //3.浮点型
            // float 存储7/8位有效数字 根据编译器不同 有效数字可能不同
            // float类型的数据在后面加f，因为C#默认声明的浮点数是double类型的

            // double 存储15/17位有效数字

            //decimal 存储27/28位的有效数字 不建议使用，需要在后面加m转为decimal类型

            //4.特殊类型
            // bool true false 表示真假的数据类型
            // char 用来存储单个字符的变量类型 字符类型 赋值时用''
            // string 用来存储多个字符的 没有上限的字符串类型赋值时用 ""

            #endregion

            #region 知识点三 变量的存储空间
            //sizeof可以获取变量类型所占的内存空间（单位：字节）
            Console.WriteLine(sizeof(short));
            #endregion

            #region 知识点四 变量命名规则

            //1.不能重名
            //2.不能以数字开头
            //3.不能使用程序关键字命名
            //4.不能有特殊符号（下划线除外）

            #endregion

            #region 知识点五 常用的命名规则

            //驼峰法命名法 首个单词首字母小写，之后单词首字母大写（变量命名法）

            //帕斯卡命名法 所有单词首字母都大写 （函数 类）

            //C#中区分字母大小写

            #endregion


            //C#所有的变量类型分为值类型和引用类型
            // 引用类型： string 数组 类
            // 值类型： 其他的变量类型 结构体

            #region 值类型和引用类型的区别

            //值类型
            int a = 5;

            //引用类型
            int[] arr = new int[] { 1, 2, 3, 4 };

            //声明了一个b让其等于之前的a
            int b = a;
            //声明了一个arr2让其等于之前的arr
            int[] arr2 = arr;
            //b = 10;
            a = 6;
            arr2[0] = 5;
            Console.WriteLine("a = {0},b = {1}",a,b);
            Console.WriteLine("arr[0] = {0},arr2 = {1}", arr[0], arr2[0]);

            //值类型 在相互赋值时 把内容拷贝给了对方 它变我不变
            //引用类型的相互赋值 是 让两者指向同一个值 它变我也变

            //2.为什么有以上区别
            //值类型 和 引用类型 存储在的 内存区域 是不同的 存储方式是不同的
            // 所以就造成了 他们在使用上的区别

            //值类型存储在栈空间 -- 系统分配，自动回收，小而快
            //引用类型 存储在 堆空间 -- 手动申请 和 释放 大而慢

            // string 这个类型比较特殊 虽然是引用类型的特征 堆空间存储 但是 是值类型的 它变我不变
            //string 重新赋值会产生内存垃圾 
            #endregion

            //通过断点调试 在监视窗口查看 内存信息
            string str1 = "123";
            string str2 = str1;
            str2 = "321";
            Console.WriteLine(str1);
            Console.WriteLine(str2);

        }
    }
}
```

![image-20221022105824129](https://cdn.jsdelivr.net/gh/PopuDiver/Typora-MapDepot/Typora-MapDepot202211091926392.png)

## Lesson3_常量

```c#
using System;

namespace Lesson3_常量
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("常量");

            #region 知识点一 常量的声明
            //关键字 const
            //固定写法：
            // const 变量类型 变量名 = 初始值;

            #endregion

            #region 知识点二 常量的特点
            //1.必须初始化
            //2.不能被修改
            //作用：声明一些常用的不变的量

            #endregion
        }
    }
}
```

## Lesson4_转义字符串

```c#
using System;

namespace Lesson4_转义字符串
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("转义字符串");

            #region 知识点一 转义字符的使用
            //什么是转义字符
            //它是字符串的一部分 用来表示一些特殊含义的字符
            //比如：在字符串中表现 单引号 引号 空行等

            #endregion

            #region 固定写法
            //固定写法 \字符
            //不同的 \ 和字符的组合表示不同的含义

            //常用的转义字符
            //单引号 \'
            //双引号 \"
            //换行 \n
            //斜杠 \\


            //不常用转义符
            // 制表符 （空一格tab键）\t
            //光标退格 \b
            // 空字符 \0


            //警报音
            // \a
            Console.WriteLine("\a");
            #endregion

            #region 知识点二 取消转义字符

            string str = @"haha\haha";


            #endregion
        }
    }
}
```

## Lesson5_类型转换

```c#
using System;

namespace Lesson5_类型转换
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("隐式转换");

            //类型转换就是不同变量类型之间的相互转换

            //隐式转换的基本规则 -> 不同类型之间自动转换
            //大范围装小范围

            #region 知识点一 相同大类型之间的转换

            //有符号 long -> int -> short -> sbyte
            //隐式转换 可以int转换为long 
            //只能用大范围装小范围的（隐式转换）


            //无符号 ulong -> uint -> ushort -> byte


            //浮点数 decimal     double float
            //decimal 这个类型无法隐式转换去存储 double 和 float
            //float 可以隐式转换成 double类型


            //特殊类型 bool char string
            //无法进行隐式转换

            #endregion

            #region 知识点二 不同大类型之间的转换

            	#region 无符号和有符号之间
                //无符号 不能装负数的
                //无符号装有符号 
                // 有符号的变量不能够隐式转换成无符号的 因为有负数存在


                //有符号装无符号
                //可以进行隐式转换，
                //但是前提是无符号的数据类型存储范围必须小于有符号的数据类型的范围


                #endregion

            	#region 浮点数和整数（有无符号）之间

                //浮点数可以装载任何类型的整数的
                //因为浮点数比整型的范围都要大

                //decimal 虽然不能隐式存储float 和 double
                //但是decimal可以隐式存储整型

                //整数装浮点数 整数是不能隐式存储浮点数的 因为整数不能存储小数

                #endregion

            #region 特殊类型和其他类型之间 相互隐式转换

            //bool 没有办法和其他类型进行隐式转换

            //char 没有办法隐式存储其它类型的变量
            //char类型 可以隐式转换成整型和浮点型
            //隐式转换成数值类型是对应的数字 对应的ASCII码

            //string类型无法与其他类型进行隐式转换

            #endregion

            #endregion

            //总结 隐式转换规则
            //高精度（大范围） 装低精度（小范围）
            //double -> float -> 整数(有无符号) -> char
            //decimal -> 整数(有无符号) -> char
            //string 和 bool 不参与隐式转换
        }
    }
}
```

## Lesson6_类型转换-显式转换

```c#
using System;

namespace Lesson6_类型转换_显式转换
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("显式转换");

            // 显式转换 -> 手动处理 强制转换

            #region 知识点一 括号强转

            //作用 一般情况下 将高精度的类型强制转换为低精度
            // 语法： 变量类型 变量名 = （变量类型）变量
            // 注意： 精度问题 范围问题

            //相同大类的整型
            //有符号的整型

            //括号强转 可能会出现范围问题造成的异常

            //浮点之间 float 和 double 之间会出现精度丢失

            //无符号和有符号 可能会出现范围报错

            //浮点和整型 会有精度丢失

            //char和数值类型

            //bool 和 string
            //不支持括号强转

            #endregion

            #region 知识点二 Parse法

            //作用 把字符串类型转换为对应的类型
            //语法 变量类型.Parse("字符串")
            //注意 字符串必须能够转换成对应类型 否则报错

            //有符号
            string i = "10000";
            int a = int.Parse(i);
            Console.WriteLine(a);
            int b = int.Parse("1");
            //无符号

            //浮点型

            //特殊类型

            #endregion

            #region 知识点三 Convert法

            //作用 更准确的将各个类型之间进行相互转换
            //语法： Convert.To目标类型（变量或常量）
            //注意： 填写的变量或常量必须正确 否则出错

            //这个方法精度更高，会四舍五入，比括号强转精度高
            //也可以将bool类型转为数值类型

            int c = Convert.ToInt32(1.5323);
            Console.WriteLine(c);

            float f = Convert.ToSingle("1.23");


            #endregion

            #region 知识点四 其他类型转string

            //作用 拼接打印
            //语法： 变量.ToString

            string str = 1.ToString();

            //直接使用 + 会默认调用这个ToString

            #endregion
        }
    }
}
```

## Lesson7_异常捕获

```c#
using System;

namespace 异常捕获
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("异常捕获");

            #region 作用

            //通常对异常捕获的学习，可以避免当代码报错的时候 造成程序卡死的情况

            #endregion

            #region 基本语法

            //必备部分
            try
            {
                //希望进行异常捕获的代码块放入其中
                //如果try中的代码报错了，不会使程序卡死
            }
            catch(Exception e)
            {
                //如果出错 会执行 catch中的代码 来捕获异常
                //catch(Exception e)具体的报错跟踪
                throw;
            }
            //可选部分
            finally
            {
                //最后执行的代码，不管有没有出错，都会执行
            }
            //注意：异常捕获代码基本结构中不需要加；
            //在里面写代码逻辑时，每一句代码，才需要去加；
            #endregion

            #region 实践

            try
            {
                Console.WriteLine(Convert.ToInt32(Console.ReadLine()));
            }
            catch
            {
                Console.WriteLine("请输入合法数字");
            }
            finally
            {
                Console.WriteLine("执行完毕");
            }

            #endregion
        }
    }
}
```

## Lesson8_算术运算符

```c#
using System;

namespace Lesson8_算术运算符
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("算数运算符");

            #region 赋值符号

            //=赋值符号，将后面的值赋给前面的变量

            #endregion

            #region 算数运算符

            // + - * / %
            // 简单的算数运算符

            #endregion

            #region 算数运算符的优先级

            //优先级 是指 在混合运算时的运算顺序

            //乘除取余 优先级高于 加减 

            //括号可以改变优先级 

            //多组括号可以从最里层开始往外算

            #endregion

            #region 复合运算符

            // += -= *= /= %=
            //复合运算符，相当于 i = i + x;

            #endregion

            #region 自增自减

            //a++ 先用再加
            //++a 先加再用

            //a-- --a同理

            #endregion
        }
    }
}
```

## Lesson9_字符串拼接方式

```c#
using System;

namespace Lesson9_字符串拼接方式
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("字符串拼接");

            #region 字符串拼接方式1

            /*算数运算符拼接
             * **/

            string str = "123";
            str += "21";
            str = str + 1;
            str += 1 + 2 + 3 + 4;//此处，拼接的字符是1 + 2 + 3 + 4的结果，而不是这一串字符
            str += "" + 1 + 2 + 3 + 4;//此处，拼接的字符串是 1 + 2 + 3 + 4 作为字符串进行拼接
            //因为，以算术运算符第一个接触的字符类型，来进行字符的拼接
            str += 1 + 2 + "" + 3 + 4;//在接触到空字符的时候，会发生拼接类型转换 


            #endregion

            #region 字符串拼接方式2

            //固定语法：
            //string.Format("待拼接内容"，内容1，内容2，....)；
            //拼接内容中的固定规则物
            //想要被拼接的内容用占位符代替{数字} 数字 0 - n  依次往后

            string str1 = string.Format("我是{0}，我今年{1}岁，我想要{2}", "balabala", 20, "xxxxxx");
            Console.WriteLine(str1);

            #endregion

            #region 控制台打印拼接

            Console.WriteLine("A{0},B{1},C{2}", 123, 456, 789);

            #endregion
        }
    }
}
```

## Lesson10_逻辑运算符

```c#
using System;

namespace Lesson_10逻辑运算符
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("逻辑运算符");

            #region 逻辑运算符的优先级

            /*
             逻辑运算符优先顺序
                !运算的优先级最高，&& 运算符的优先级大于 || 运算符
                逻辑运算符的优先级都低于 算数运算符 条件运算符 （! 运算除外）
             */

            #endregion

            #region 逻辑运算符的短路问题

            /*
             满足前一个条件之后，就直接进行短路，后面的程序不会进行运行
                && ： 如果前面的代码已经为 false ，表示此条语句已经为假， 后面的程序就不会运行
                || ： 如果前面的代码已经为 true ，表示此条语句已经为真， 后面的程序就不会运行
            这两种情况都会发生短路
             */

            #endregion
        }
    }
}

```

## Lesson11_位运算符

```c#
using System;

namespace Lesson_11位运算符
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("位运算符");
            //位运算符 主要用数值类型进行计算
            //将数值转换为2进制 再进行位运算

            #region 位与 &
            //规则 连接两个数值进行位运算 将数值转为2进制
            //对位运算 有0则0

            int a = 1; // 001
            int b = 5; // 101
            int c = a & b;
            Console.WriteLine(c);

            #endregion

            #region 位或 |
            //规则 连接两个数值进行位计算 将数值转为2进制
            //对位运算 有1则1


            #endregion
            
            #region 异或 ^
            //规则 连接两个数值进行位计算 将数值转为2进制
            //对位计算 相同为0 不同为1


            #endregion

            #region 位取反 ~
            //规则 写在数值前面 将数值转为2进制
            //对位运算 0变1 1变0

            a = 5;//    0000 0000 0000 0000 0000 0000 0000 0101
                  //~   1111 1111 1111 1111 1111 1111 1111 1010     //原码
                  //    1000 0000 0000 0000 0000 0000 0000 0101     //反码
                  //    1000 0000 0000 0000 0000 0000 0000 0110     //补码    = -6

            b = ~a;
            Console.WriteLine(b);

            #endregion

            #region 左移 << 和 右移 >> 
            //规则 让一个数的2进制数进行左移和右移
            //左移几位 右侧加几个0

            //右移几位 右侧去掉几个数

            #endregion

        }
    }
}
```

## Lesson12_枚举

```c#
using System;

namespace Lesson12_枚举
{
    #region 知识点一 基本概念
    //枚举是一个被命名的整型常量的集合，一般用它来表示 状态 类型 等

    #region 1. 申明枚举 和 申明枚举变量
    //申明枚举： 相当于是创建一个自定义的枚举类型
    //申明枚举变量： 使用申明的自定义的枚举类型， 创建一个枚举变量
    #endregion

    #region  2. 申明枚举语法
    //枚举名 以E或者E_开头 作为我们的命名规范
    enum E_自定义枚举名
    {
        自定义枚举项名字,   //  枚举中包裹的 整型常量 第一个默认值是0 下面会依次累加
        自定义枚举项名字0 = 5,  //  枚举项默认值变为 5 ，后面的也会一直默认累加
        自定义枚举项名字1,  //  6
        自定义枚举项名字2,  //  7
    }

    #endregion

    #endregion

    #region 知识点二 在哪里申明枚举
    //1.namespace 语句块中 （常用）
    //2.class语句块中 struct语句块中
    //注意：枚举不能在函数语句块中申明

    enum E_MonsterType
    {
        Normal,
        Boss
    }

    enum E_PlayerType
    {
        Main,
        Other
    }

    #endregion


    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("枚举");

            #region 知识点三 枚举的使用
            //申明枚举变量
            //自定义的枚举类型 变量名 = 默认值;（自定义的枚举类型.枚举项）
            E_PlayerType playType = E_PlayerType.Main;

            if(playType == E_PlayerType.Main)
            {
                Console.WriteLine("主玩家逻辑，代号{0}",playType);
            }
            else if(playType == E_PlayerType.Other)
            {
                Console.WriteLine("其他玩家逻辑，代号{0}", playType);
            }

            //switch 和 枚举 非常契合
            E_MonsterType monsterType = E_MonsterType.Boss;
            switch (monsterType)
            {
                case E_MonsterType.Normal:
                    Console.WriteLine("普通怪物逻辑");
                    break;
                case E_MonsterType.Boss:
                    Console.WriteLine("Boss逻辑");
                    break;
                default:
                    break;
            }

            #endregion

            #region 知识点四 枚举的类型转换

            //1.枚举和int互相转换
            int i = (int)playType;
            Console.WriteLine(i);
            //int 转枚举
            playType = (E_PlayerType)3;
            Console.WriteLine(playType);

            //2.枚举和string相互转换
            string str = monsterType.ToString();
            Console.WriteLine(str);
            //string 转换为 枚举
            //Parse后 第一个参数： 你要转为的是哪个 枚举类型 第二个参数 ： 用于转换的对应枚举项的字符串
            // 转换完毕后 是一个通用的类型 我们需要用括号强转成我们想要的目标枚举类型
            playType = (E_PlayerType)Enum.Parse(typeof(E_PlayerType), "Other");
            Console.WriteLine(playType);


            #endregion

            #region 知识点五 枚举的作用
            //在游戏开发中，对象有很多时候 会有许多状态
            //比如玩家 有一个动作状态 我们需要用一个变量或者标识 来表示当前玩家处于的是哪种状态
            //枚举可以帮助我们 清晰的分清楚状态的含义

            #endregion
        }
    }      
}
```

## Lesson13_数组

```c#
using System;

namespace Lesson13_数组
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("数组");

            #region 一维数组

            #region 知识点一 基本概念

            //数组是存储一组相同类型数据的集合
            //数组分为 一维 多维 交错数组
            //一般情况 一维数组简称为数组

            #endregion

            #region 知识点二 数组的申明

            //变量类型[] 数组名;   //只是申明了一个数组 但是并没有开辟空间

            //变量类型[] 数组名 = new 变量类型[数组长度];
            int[] arr = new int[5];//开辟了空间，但是默认初始化为0

            //变量类型[] 数组名 = new 变量类型[数组长度]{内容1，内容2，······};
            int[] arr1 = new int[5] { 1,2,3,4,5};//开辟了空间，初始化值

            //变量类型[] 数组名 = new 变量类型[]{内容1，内容2，······};
            int[] arr2 = new int[] { };//大括号里有多少个内容，决定数组长度

            //变量类型[] 数组名 = {内容1，内容2，······}；
            int[] arr3 = { 1, 2, 3, 4, 5 };//大括号里有多少个内容，决定数组长度

            #endregion

            #region 数组的使用

            int[] array = { 1, 2, 3, 4, 5 };
            //1.数组的长度
            Console.WriteLine(array.Length);

            //2.获取数组中的元素
            //数组中的下标和索引 从零开始
            Console.WriteLine(array[2]);

            //3.修改数组中的元素
            array[0] = 5;
            Console.WriteLine(array[0]);

            //4.遍历数组 通过循环 快速获取数组中的每一个元素

            //5.增加数组的元素
            //数组初始化之后 不能直接添加新的元素 只能申请一个新的数组 将新的数组赋给本数组 重新初始化实现增加元素的目的

            //6.删除数组的元素
            //数组初始化之后 不能直接删除元素 也需要申请一个新的数组 将新的数组赋给本数组 重新初始化实现增加元素的目的

            //7.查找数组中的元素 循环遍历查找

            #endregion

            #endregion

            /*
             * 总结
             * 1.概念：同一变量类型的数据集合
             * 2.一定要掌握的知识：声明 遍历 增删查改
             * 3.所有的变量类型都可以声明为数组
             * 4.他是用来批量存储游戏中的同一类型对象的 容器
             * **/

        }
    }
}
```

## Lesson14_二维数组

```c#
using System;

namespace Lesson14_二维数组
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("二维数组");

            #region 知识点一 基本概念

            //二维数组是使用两个下标来确定元素的数组

            #endregion

            #region 知识点二 二维数组的声明

            //变量类型[行,列] 二维数组名
            int[,] arr;

            //变量类型[,] 二维数组变量名 = new 变量类型[行,列];
            int[,] arr2 = new int[3, 3];

            //变量类型[,] 二维数组变量名 = new 变量类型[行,列]{ { 0行内容0，0行内容1······ },{···} };
            int[,] arr3 = new int[3, 3] { { 0, 1, 2 }, { 1, 2, 3 }, { 3, 4, 5 } };

            //变量类型[,] 二维数组变量名 = new 变量类型[,]{ { 0行内容0，0行内容1······ },{···} };
            int[,] arr4 = new int[,] { { 0, 1, 2 }, { 1, 2, 3 }, { 3, 4, 5 } };

            //变量类型[,] 二维数组变量名 = { { 0行内容0，0行内容1······ },{···} };
            int[,] arr5 = { { 0, 1, 2 }, { 1, 2, 3 }, { 3, 4, 5 } };


            #endregion

            #region 知识点三 二维数组的使用
            int[,] array = new int[,]{{1,2,3},
                                      {2,3,4}
                                      };

            //1.二维数组的长度
            Console.WriteLine(array.GetLength(0));
            Console.WriteLine(array.GetLength(1));

            //2.获取二维数组中的元素

            //3.修改二维数组中的元素

            //4.遍历二维数组

            //5.增加数组的元素
            //数组 声明初始化过后 就不能在原有的基础上进行添加或者删除了 只能使用搬家法

            //6.删除数组的元素

            //7.查找数组中的元素

            #endregion

            /*
             * 总结：
             * 1.概念 同一变量类型的行列数据集合
             * 2.一定要掌握 声明遍历增删查改
             * 3.所有的变量类型都可以声明为二维数组
             * 4.游戏中一般用来存储矩阵 再控制台小游戏中可以用二维数组来表示地图格子
             * 
             * **/

        }
    }
}
```

## Lesson15_交错数组

```c#
using System;

namespace Lesson15_交错数组
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("交错数组");

            #region  知识点一 基本概念

            //交错数组 是 数组的数组 每个维度的数量都可以不同

            //注意 二维数组的每行的列数相同 交错数组每行的列数可能不同

            #endregion

            #region 知识点二 数组的声明

            //变量类型[][] 交错数组名;
            int[][] arr1;

            //变量类型[][] 交错数组名 = new 变量类型[行数][];
            int[][] arr2 = new int[3][];

            //变量类型[][] 交错数组名 = new 变量类型[行数][]{一维数组1，一维数组2......};
            int[][] arr3 = new int[3][] {new int[] {1,2,3},
                                         new int[]{1,2},
                                         new int[]{1,2,3,4}
                                        };

            //变量类型[][] 交错数组名 = new 变量类型[][]{一维数组1，一维数组2......};
            int[][] arr4 = new int[][] {new int[] {1,2,3},
                                         new int[]{1,2},
                                         new int[]{1,2,3,4}
                                         };

            #endregion

            #region 知识点三 数组的使用
            int[][] array = {new int[] {1,2,3},
                             new int[]{4,5}
                            };
            //1.数组的长度

            //行
            Console.WriteLine(array.GetLength(0));
            Console.WriteLine(array[0].Length);

            //2.获取交错数组中的元素

            Console.WriteLine(array[0][1]);

            //3.修改交错数组中的元素

            array[0][1] = 99;
            Console.WriteLine(array[0][1]);

            //4.遍历交错数组

            //5.增加交错数组的元素

            //6.删除交错数组的元素

            //7.查找交错数组中的元素

            #endregion

            //总结：
            //1.概念：交错数组 可以存储同一类型的m行不确定列的数据
            //2.一定要掌握的 声明遍历增删查改
            //3.所有的变量类型都可以声明 交错数组

        }
    }
}
```

## Lesson16_Function

```c#
using System;

namespace Lesson16_Function
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("函数");

            #region 知识点一 基本概念

            /*
             * 函数
             * 本质是一块具有名称的代码块
             * 可以使用函数的名称来执行该代码块
             * 函数是封装代码进行重复使用的一种机制
             * **/

            /*
             * 函数的主要作用
             * 1.封装代码
             * 2.提升代码复用率
             * 3.抽象行为
             * **/

            #endregion

            #region 知识点二 函数写在哪里

            //1.class语句块中
            //2.struct 语句块中

            #endregion

            #region 知识点三 基本语法

            /*
             *   static 返回类型 函数名(参数类型 参数名1,.........){
             *          函数的代码逻辑;
             *          .............
             *          return 返回值;(如果有返回类型才返回)
             *   }
             *
             * **/

            /*
             * 1.关于static 不是必须的 在没有学习类和结构体之前都是必须写的
             * 
             * 2-1.关于返回类型 引出一个新的关键字 void(表示没有返回值)
             * 2-2.返回类型可以写任意的变量类型 14种变量类型 + 复杂数据类型(数组 枚举 结构体 类)
             * 
             * 3.关于函数名 使用帕斯卡命名法命名 MyName(每一个单词首字母都大写)
             * 
             * 4-1.参数不是必须的 可以有0-n个函数 参数的类型 也是可以是任意类型的 14种变量类型 + 复杂数据类型
             * 多个参数的时候 用，隔开
             * 4-2.参数名 驼峰法命名
             * 
             * 5.当返回值类型不为void 时 必须通过新的关键词 return返回对应类型的内容 (即使是void也可以使用						return)
             * **/

            #endregion

            #region 知识点四 实际运用

            /*
             * 1.无参无返回值函数
             * 
             * 2.有参无返回值函数
             * 
             * 3.无参有返回值函数
             * 
             * 4.有参有返回值函数
             * 
             * 5.有参多返回值函数
             * **/

            #endregion

            #region 知识点五 关于return

            #endregion

            /*
             * 总结：
             * 1.基本概念
             * 2.函数写在哪里 - class 或者 struct 中
             * 3.基本语法
             * 4. return 可以提前结束函数逻辑 程序是线性执行的 从上到下执行
             * **/

        }
    }
}
```

## Lesson17_ref和out

```c#
using System;

namespace Lesson17_ref和out
{
    class Program
    {
        //ref的使用
        static void ChangeValueRef(ref int value)
        {
            value = 3;
        }

        static void Main(string[] args)
        {
            Console.WriteLine("ref 和 out");

            #region 知识点一 学习ref和out的原因

            /*
             * 学习ref和out的原因
             * 它们可以解决 在函数内部改变外部传入的内容 里面变了 外面也要变
             * **/

            #endregion

            #region 知识点二 ref和out的使用

            /*ref
             * 函数参数的修饰符
             * 当传入的值类型参数在内部修改时 或者引用类型参数在内部重新声明时
             * 外部的值会发生变化
             * **/

            int a = 1;
            ChangeValueRef(ref a);
            Console.WriteLine(a);

            #endregion

            #region 知识点三 ref和out的区别

            /*
             * 1.ref传入的变量必须初始化 out不用
             * 2.out传入的变量必须在内部赋值 ref不用
             * **/


            /*
             * ref传入的变量必须初始化 但是在内部 可改可不改
             * out传入的变量 不用初始化 但是在内部 必须修改值
             * **/
            #endregion

            //总结
            //1.ref和out的作用：解决值类型和引用类型 在函数内部 改值或者重新声明 能够影响外部传入的变量 让其也被修改
            //2.使用上：就是在声明参数的时候 前面加上 ref和out的关键字即可 使用时 同上
            //3.区别： ref传入的变量必须初始化 但是在内部 可改可不改
            //         out传入的变量 不用初始化 但是在内部 必须修改值
        }
    }
}
```

## Lesson18_变长参数和参数默认值

```c#
using System;

namespace Lesson18_变长参数和参数默认值
{
    class Program
    {

        #region 知识点一 函数语法复习

        #endregion

        #region 知识点二 变长参数关键词

        /*
         * 变长参数关键字 params
         * 
         * params int[] 意味着可以传入n个int参数 n可以等于0 传入的参数会存在arr数组中
         * 注意：
         * 1.params关键字后面必须为数组
         * 2.数组的类型可以是任意的类型
         * 
         * 
         * 3.函数参数可以有  别的参数和params关键字修饰的参数
         * 4.函数参数种只能最多出现一个params关键字 并且一定是在最后一组参数 前面可以有n个其他参数
         * **/

        static int Sum(params int[] arr)
        {
            int sum = 0;
            for(int i = 0;i < arr.Length; i++)
            {
                sum += arr[i];
            }
            return sum;
        }

        static void Eat(string name,params string[] things)
        {

        }

        #endregion

        #region 知识点三 参数默认值

        /*
         * 有参数默认值的参数 一般称为可选参数
         * 作用是 当调用函数时可以不传入参数 不传就会使用默认值作为参数的值
         * **/

        static void Speak(string str = "你好世界")
        {
            Console.WriteLine(str);
        }

        /*
         * 注意：
         * 1.支持多参数默认值 每个参数都可以有默认值
         * 2.如果要混用 可选参数 必须写在 普通参数后面
         * 
         * **/

        static void Speak2(string test,string name = "abaabaaba",string str = "你好世界")
        {

        }

        #endregion

        static void Main(string[] args)
        {
            Console.WriteLine("变长参数和参数默认值");

            
            Console.WriteLine(Sum(1,2,3,4,5,6));

            Speak();
        }

        /*
         * 总结：
         * 1）变长参数关键字 params
         * 作用：可以传入n个同类型参数 n可以是0
         * 注意：
         * 1.params后面必须是数组 意味着只能是同一类型的可变参数
         * 2.变长参数只能有一个
         * 3.必须在所有参数最后写变长参数
         * 
         * 2）参数默认值(可选参数)
         * 作用：可以给参数默认值 使用时可以不传参 不传用默认的 传了用传的
         * 注意：
         * 1.可选参数可以有多个
         * 2.正常参数必须写在可选参数前面 可选参数只能写在所有参数后面
         * 
         * **/

    }
}
```

## Lesson19_函数重载

```c#
using System;

namespace Lesson19_函数重载
{
    class Program
    {

        #region 知识点一 基本概念

        /*
         * 重载概念
         * 在同一语句块(class 或者 struct)中
         * 函数(方法) 名相同
         * 参数的数量不同
         * 或者 参数的数量相同 但参数的类型或顺序不同
         * 
         * **/

        /*
         * 作用：
         * 1.命名一组功能相似的函数 减少函数名的数量 避免命名空间的污染
         * 2.提升程序的可读性
         * **/

        #endregion

        #region 知识点二 实例

        /*
         * 注意：1.重载和返回值类型无关 只和参数类型 个数 顺序有关
         * 2.调用时 程序会自动根据传入的参数类型判断使用哪一个重载
         * 
         * 参数数量不同
         * 
         * 数量相同 类型不同
         * 
         * 数量相同 顺序不同
         * 
         * ref 和 out
         * 
         * **/

        static int CalcSum(int a,int b)
        {
            return a + b;
        }

        //参数数量不同
        static int CalcSum(int a,int b,int c)
        {
            return a + b + c;
        }


        //数量相同 类型不同
        static float CalcSum(float a,int b)
        {
            return a + b;
        }

        //数量相同 顺序不同
        static float CalcSum(int a, float b)
        {
            return a + b;
        }


        //ref 和 out
        //          ref传入的变量必须初始化 但是在内部 可改可不改
        //          out传入的变量 不用初始化 但是在内部 必须修改值
        static float CalcSum(ref int a, ref float b)
        {
            return a + b;
        }

        //ref和out不能单独重载
        //ref和out可以理解成 他们也是一种变量类型 所以可以用在重载中 但是 ref和out不能同时修饰相同类型相同数量相同顺序的重载
        static float CalcSum(out float a, out float b)
        {
            a = 3;
            b = 2.5f;
            return a + b;
        }
        #endregion

        static void Main(string[] args)
        {
            Console.WriteLine("函数重载");
            int a = 2;
            float b = 1.5f,c;
            Console.WriteLine(CalcSum(1, 2, 3)); 
            Console.WriteLine(CalcSum(1, 2));
            Console.WriteLine(CalcSum(1.5f, 2));
            Console.WriteLine(CalcSum(2, 1.5f));
            Console.WriteLine(CalcSum(ref a, ref b));
            Console.WriteLine(CalcSum(out c, out b));
        }

        /*
         * 总结：
         * 概念：同一个语句块中 函数名相同 参数数量 类型 顺序不同的函数 就称为我们的重载函数
         * 注意：和返回值无关
         * 作用：一般用来处理不同参数的同一类型的逻辑处理
         * **/

    }
}
```

## Lesson20_结构体

```c#
using System;

namespace Lesson20_结构体
{
    class Program
    {

        #region 知识点一 基本概念

        /*
         * 结构体 是一种自定义变量类型 类似枚举需要自己定义
         * 它是数据和函数的集合
         * 在结构体中 可以声明各种变量和方法
         * 
         * 作用：用来表现存在关系的数据集合 比如用结构体表现学生 动物 人类等
         * **/

        #endregion

        #region 知识点二 基本语法

        //1.结构体一般写在 namespace 语句块中
        //2.结构体关键字 struct 

        struct 自定义结构体名
        {
            //第一部分 变量
            //第二部分 构造函数(可选)
            //第三部分 函数
            //注意结构体名字 我们的规范是帕斯卡命名法
        }

        #endregion

        #region 知识点三 实例

        //学生的结构体
        struct Student
        {

            #region 知识点五 访问修饰符

            /*
             * 修饰结构体中变量和方法 是否能被外部使用
             * public 公开的 可以被外部访问
             * private 私有的 只能在内容使用
             * 默认不写 为private
             * 
             * **/

            #endregion


            //变量 
            //结构体声明的变量 不能直接初始化
            //变量类型 可以写任意类型 包括结构体 但是 不能是自己的结构体 可以是其他的结构体
            public int age;
            public bool sex;

            #region 知识点六 结构体的构造函数

            /*
             * 基本概念
             * 1.没有返回值
             * 2.函数名必须和结构体名相同
             * 3.必须有参数
             * 4.如果声明了构造函数 那么必须在其中对所有变量数据初始化
             * **/

            #endregion

            //构造函数

            //构造函数 一般是用于在外部方便初始化的函数
            public Student(int age,bool sex)
            {
                //需要关键字 this
                //代表自己
                this.age = age;
                this.sex = sex;
            }

            //在结构体中的方法 目前不需要加static关键字
            public void Speak()
            {
                //函数中可以直接使用结构体内部声明的变量
                Console.WriteLine(age);
            }
            //可以根据需求 写许多函数
        }

        #endregion







        static void Main(string[] args)
        {
            Console.WriteLine("结构体");

            #region 知识点四 结构体的使用

            //变量类型 变量名；
            Student s1;
            s1.age = 12;
            s1.sex = true;
            Console.WriteLine(s1.age);
            s1.Speak();
            Console.WriteLine(s1.age);

            Student s2 = new Student(18,true);
            s2.Speak();
            #endregion

        }

        /*
         * 总结：
         * 1.概念：结构体 struct 是变量和函数的集合 用来表示特定的数据集合
         * 访问修饰符：public 和 private 用来修饰变量和方法的 public 外部可以调用 private内部用 不写的话 默认是private
         * 构造函数 ：没有返回值 函数名和结构体名相同 可以重载 主要是帮助我们快速初始化结构体对象的
         * 
         * 2.注意：
         * 1.在结构体中声明的变量 不能初始化 只能在外部或者在函数中赋值(初始化)
         * 2.在结构体中声明的函数 不用加struct的
         * **/

        

    }
}
```

## Lesson21_类和对象

```c#
using System;

namespace Lesson21_类和对象
{
    class Program
    {

        #region 面向对象概念回顾

        //万物皆对象
        //用程序来抽象对象
        //用面向对象的思维来编程

        #endregion

        #region 知识点一 什么是类

        /*
         * 基本概念
         * 具有相同特征
         * 具有相同行为
         * 一类事物的抽象
         * 类是对象的模板
         * 可以通过类创建出对象
         * 类的关键词
         * class
         * **/

        #endregion

        #region 知识点二 类声明在哪里

        //类一般声明在namespace语句块中

        #endregion

        #region 知识点三 类声明的语法

        class 类名
        {
            //特征 -- 成员变量
            //行为 -- 成员方法
            //保护特征 -- 成员属性

            //构造函数和析构函数
            //索引器
            //运算符重载
            //静态成员
        }

        #endregion

        #region 知识点四 类声明实例

        //这个类是用来形容人类的
        //命名：用帕斯卡命名法
        //注意：用同一个语句块中的不同类 不能重名
        class Person
        {

        }

        //这个类用来表示机器
        class Machine
        {

        }
        #endregion

        static void Main(string[] args)
        {
            Console.WriteLine("类和对象");

            #region 知识点五 什么是类

            /*
             * 基本概念
             * 类的声明 和 类对象 声明是两个概念
             * 类的声明 类似 枚举和结构体的声明 类的声明相当于声明了一个自定义变量类型
             * 对象 是类创建出来的
             * 相当于声明了一个指定类的变量
             * 类创建 对象的过程 一般称为实例化对象
             * 类对象 都是引用类型的
             * **/

            #endregion

            #region 知识点六 实例化对象基本语法

            //类名 变量名；
            //类名 变量名 = null；（null代表空）
            //类名 变量名 = new 类名();

            #endregion

            #region 知识点七 实例化对象
            Person p;
            Person p2 = null;//null 代表空 不分配堆内存空间
            Person p3 = new Person();//相当于一个人对象
            Person p4 = new Person();//相当于又一个人对象
            //注意：
            //虽然他们是来自一个类的实例化对象
            // 但是他们的特征 行为 等等信息 都是他们独有的
            // 千万不要觉得他们是共享了数据 彼此除了共同声明的对象，没有什么关系
            #endregion

        }
    }

    /*
     * 总结：
     * 类的声明和类对象的声明是两个概念
     * 类的声明 是声明对象的模板 用来抽象显示事物的
     * 类对象的声明 是用来表示现实中的对象个体的
     * 
     * 类是一个自定义的变量类型
     * 实例化一个类对象 是在声明变量
     * **/

}
```

## Lesson22_封装__成员变量和访问修饰符

```c#
using System;

namespace Lesson22_封装_成员变量和访问修饰符
{
    class Program
    {

        #region 知识点一 成员变量
        
        /*
         * 基本规则
         * 1.声明在类语句块中
         * 2.用来描述对象的特征
         * 3.可以是任意变量类型
         * 4.数量不做限制
         * 5.是否赋值根据需求来定
         * **/

        #endregion

        //性别枚举
        enum E_SexType
        {
            Man,
            Woman
        }

        //位置结构体
        struct Position
        {

        }

        //宠物类
        class Pet
        {

        }

        class Person
        {
            // 特征 -- 成员变量
            // 姓名
            string name = "Hello World!";
            //年龄
            int age;
            //性别
            E_SexType sex;
            //如果在类中声明一个和自己相同类型的成员变量时
            //不能对它进行实例化
            Person per = null;
            //朋友
            Person[] boyFriend;
            //位置
            Position pos;
            //宠物
            Pet pet;
        }

        #region 知识点二 访问修饰符

        /*
         * public -- 公共的 内部和外部都能访问和使用
         * private -- 私有的 内部才能访问和使用 不写访问修饰符 默认为private
         * protected -- 保护的 内部和子类才能访问和使用
         * 目前决定类内部的成员和访问权限
         * **/

        #endregion

        static void Main(string[] args)
        {
            Console.WriteLine("封装_成员变量和访问修饰符");

            Person p = new Person();

            #region 知识点三 成员变量的使用和初始值

            //值类型来说 数字类型 默认值都是0 bool类型 false
            //引用类型 null
            //default方法可以查看默认值
            Console.WriteLine(default(int));

            #endregion

        }

        /*
         * 总结：
         * 成员变量 
         * 描述特征
         * 类中声明
         * 赋值随意
         * 默认值，值各不相同
         * 默认值 引用为null
         * 任意类型
         * 任意数量
         * **/

    }
}
```

## Lesson23_封装__成员方法

```c#
using System;

namespace Lesson23_封装_成员方法
{

    #region 知识点一 成员方法声明

    /*
     * 基本概念
     * 成员方法 用来表现对象行为
     * 1.声明在类语句块中
     * 2.是用来描述对象的行为的
     * 3.规则和函数声明规则相同
     * 4.受到访问修饰符规则影响
     * 5.返回值参数不做限制
     * 6.方法数量不做限制
     * **/

    /*
     * 注意：
     * 1.成员方法不要加关键字static
     * 2.成员方法 必须实例化出对象 再通过对象来使用 相当于该对象执行了某个行为
     * 3.成员方法 受到访问修饰符影响
     * **/
    #endregion

    class Person
    {
        public string name;
        public int age;

        /// <summary>
        /// 说话的行为
        /// </summary>
        /// <param name="str"></param>
        public void Speak(string str)
        {
            Console.WriteLine("{0}说{1}",name,str);
        }
    }


    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("成员方法");

            #region 知识点二 成员方法的使用

            //2.成员方法 必须实例化出对象 再通过对象来使用 相当于该对象执行了某个行为
            Person p = new Person();
            p.name = "jijijiji";
            p.Speak("abaabaaba");

            #endregion
        }
    }

    /*
     * 总结：
     * 成员方法
     * 描述行为
     * 类中声明
     * 任意数量
     * 返回值和参数根据需求决定
     * **/

}
```

## Lesson24_析构函数和构造函数

```c#
using System;

namespace Lesson24_析构函数和构造函数
{

    #region 知识点一 构造函数

    /*
     * 基本概念
     * 在实例化对象时 会调用的用于初始化的函数
     * 如果不写 默认存在一个无参构造函数
     * **/

    /*
     * 构造函数的写法
     * 1.没有返回值
     * 2.函数名和类名必须相同
     * 3.没有特殊需求时 一般都是public的
     * **/

    class Person
    {
        public string name;
        public int age;

        public Person()
        {
            name = "Animator";
            age = 15;
        }

        public Person(int age)
        {
            //this代表当前调用该函数的对象自己
            this.age = age;
        }

        public Person(string name)
        {
            this.name = name;
        }

        public Person(int age,string name):this(name)
        {
            Console.WriteLine(name + age + age);
        }

        //当引用类型的堆内存被回收时
        //析构函数 是当垃圾 真正被回收的时候 才会调用的函数

        ~Person(){

        }

    }

    /*
     * 4.构造函数可以被重载
     * 5.this代表当前调用该函数的对象是自己
     * **/

    /*
     * 注意：
     * 如果不自己实现无参构造函数而实现了有参构造函数
     * 会失去默认的无参构造
     * **/

    #endregion

    #region 知识点二 构造函数的特殊写法

    //可以通过 this 重用构造函数代码
    //访问修饰符 构造函数名(参数列表): this(参数1，参数2......)

    #endregion

    #region 知识点三 析构函数

    /*
     * 基本概念
     * 当引用类型的堆内存被回收时 会调用该函数
     * 对于需要手动管理内存的语言 需要在析构函数中做一些内存回收处理
     * 但是C#中存在自动垃圾回收机制GC
     * 所以我们几乎不会怎么使用析构函数 除非你想在某一个对象被垃圾回收时 做一些特殊处理
     * 注意：
     * 在unity开发中析构函数几乎不会使用 所以该知识点只做了解
     * **/

    /*
     * 基本语法
     * ~类名(){}
     * **/


    #endregion

    #region 知识点四 垃圾回收机制

    /*
     * 垃圾回收 英文简写GC(Garbage Collector)
     * 垃圾回收的过程是在遍历堆(Heap)上动态分配的所有对象
     * 通过识别他们是否被引用来确定哪些对象是垃圾 哪些对象仍要被使用
     * 所谓的垃圾就是没有被任何变量 对象引用的内容
     * 垃圾就需要被回收释放
     * **/

    /*
     * 垃圾回收有很多种算法 比如
     * 引用计数(Reference Counting)
     * 标记清除(Mark Sweep)
     * 标记整理(Mark Compact)
     * 复制集合(Copy Collection)
     * **/

    /*
     * 注意：
     * GC只负责堆内存的垃圾回收
     * 引用类型都是存在堆中的 所以它的分配和释放都通过垃圾回收机制来管理
     * **/

    /*
     * 栈(Stack)上的内存是由系统自动管理的
     * 值类型在栈(Stack)中分配内存的 他们有自己的生命周期 不用对它们进行管理，会自动分配和释放
     * **/

    /*
     * C#中内存回收机制的大概原理：
     * 0代内存     1代内存    2代内存
     * 代的概念：
     * 代是垃圾回收机制使用的一种算法(分代算法)
     * 新分配的对象都会被配置在第0代内存中
     * 每次分配都可能会进行垃圾回收以释放内存(0代内存满时)
     * **/

    /*
     * 在一次内存回收过程开始时 垃圾回收器会认为堆中全是垃圾 会进行以下两步
     * 1.标记对象 从根(静态字段 方法参数) 开始检查引用对象 标记后为可达对象 未标记为不可达对象
     * 不可达对象就认为是垃圾
     * 2.搬迁对象压缩堆  (挂起执行托管代码线程) 释放未标记的对象 搬迁可达对象 修改引用地址
     * **/

    /*
     * 大对象总被认为是第二代内存 目的是减少性能损耗 提高性能
     * 不会对大对象进行搬迁压缩 85000字节(83kb) 以上的对象为大对象
     * **/

    #endregion

    class Program
    {


        static void Main(string[] args)
        {
            Console.WriteLine("构造函数和析构函数");

            Person p = new Person();
            Console.WriteLine(p.name + p.age);

            //手动触发垃圾回收的方法
            //一般情况下 不会频繁调用
            //一般是在loading条读取时 调用
            GC.Collect();
        }
    }

    //总结：
    //构造函数
    //实例化对象时 调用的函数
    //主要用来初始化成员变量

    //基本语法
    //不写返回值
    //函数名和类名相同
    //访问修饰符根据需求而定
    //一般为public

    //注意：
    //可以重载构造函数
    //可以用this语法重用代码
    //可以在函数中用this区分同名参数和成员变量
    //有参构造会顶掉默认的无参构造

    //析构函数
    //当对象被垃圾回收时 调用的 主要是用来回收资源或者特殊处理内存的

    //基本语法
    //不写返回值
    //不写修饰符
    //不能有参数
    //函数名和类名相同
    //前面加~

}
```

## Lesson25_成员属性

```c#
using System;

namespace Lesson25_成员属性
{

    #region 知识点一 成员属性的基本概念

    /*
     * 基本概念
     * 1.用于保护成员变量
     * 2.为成员属性的获取和赋值添加逻辑处理
     * 3.解决private public protected 的局限性
     *    属性可以让成员变量在外部
     *    只能获取不能修改 或者 只能修改不能获取
     * **/

    #endregion

    #region 知识点二 成员属性的基本语法

    /*  访问修饰符 属性类型 属性名{
     *      get{}
     *      set{}
     *  }
    **/

    class Person
    {
        private string name;
        int age;
        int money;
        bool sex;

        //属性的命名一般使用 帕斯卡命名法
        public string Name
        {
            get
            {
                //可以在返回值前 添加一些逻辑规则
                //意味着这个属性可以获取的内容
                return name;
            }
            set
            {
                //可以在设置之前添加一些逻辑规则
                //关键字 value 用于表示外部传入的值
                name = value;
            }
        }

        #region 知识点四 成员属性中 get 和 set 前可以加访问修饰符

        /*
         * 注意：
         * 1.默认不加会使用属性声明时的访问权限
         * 2.加的访问修饰符要低于属性的访问权限
         * 3.不能让get和set的访问权限都低于属性的权限
         * **/

        #endregion



        public int Money
        {
            //不能将两个属性都使用可访问修饰符
            get
            {
                //解密处理
                return money - 5;
            }
            set
            {
                //加密处理
                money = value + 5;
            }
        }

        #region 知识点五 get 和 set 可以只有一个

        //只有一个时 没必要加访问修饰符
        //一般情况下 只会出现 只有get的情况 很少会出现只有set的情况

        #endregion

        public bool Sex{
            get
            {
                return sex;
            }
        }

        #region 知识点六 自动属性

        /*
         * 作用：外部能得不能改的特征
         * 如果类中有一个特征是只希望外部能得不能改的 又没什么特殊处理
         * 那么可以直接使用自动属性
         * **/
        #endregion

        public float Height
        {
            //没有在set和get中写逻辑需求或者想法
            get;
            private set;
        }


    }

    #endregion


    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("成员属性");
            #region 知识点三 成员属性的使用
            Person p = new Person();
            p.Name = "Animator";
            Console.WriteLine(p.Name);
            p.Money = 5;
            Console.WriteLine(p.Money);
            

            #endregion
        }
    }

    /*
     * 总结：
     * 1.成员属性概念：一般是用来保护成员变量的
     * 2.成员属性的使用和变量一样 外部用对象点出
     * 3.get中需要return内容；set中用value表示传入的内容
     * 4.get和set语句块中可以加逻辑处理
     * 5.get和set可以加访问修饰符 但是要按照一定的规则进行添加
     * 6.get和set可以只有一个
     * **/

}
```

## Lesson26_索引器

```c#
using System;

namespace Lesson26_索引器
{

    #region 知识点一 索引器基本概念

    //基本概念
    //让对象可以像数组一样通过索引访问其中元素 使程序看起来更直观 更容易编写

    #endregion

    #region 知识点二 索引器语法

    /*
     *  访问修饰符 返回值 this[参数类型 参数名 ， 参数类型 参数名......]
     *  {
     *      内部的写法和规则和索引器相同
     *      get{}
     *      set{}
     *  }
     * **/

    class Person
    {
        private string name;
        private int age;
        private Person[] friends;
        private int[,] array;

        public Person this[int index]
        {
            get
            {
                return friends[index];
            }
            set
            {
                //value代表传入的值
                friends[index] = value;
            }
        }

        #region 知识点五 索引器可以重载

        //重载的概念是 -- 函数名相同 参数类型 数量 顺序不同

        public int this[int i,int j]
        {
            get
            {
                return array[i, j];
            }
            set
            {
                array[i, j] = value;
            }
        }

        #endregion

    }

    #endregion

    #region 知识点四 索引器中可以写逻辑

    //get和set中是可以写逻辑的 根据需求来处理这里面的内容

    #endregion

        
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("索引器");

            #region 知识点三 索引器的使用

            Person p = new Person();
            p[0] = new Person();


            p[0, 0] = 10;
            #endregion

        }
    }

    /*
     * 总结：
     * 索引器对于我们来说的主要作用
     * 可以让我们以中括号的形式访问自定义类中的元素 规则自己定 访问时和数组一样
     * 比较适用于 在类中有数组变量时使用 可以方便的访问和进行逻辑处理
     * 
     * 固定写法
     * 访问修饰符 返回值 this[参数列表]
     * get 和 set 语句块
     * 可以重载
     * 
     * 结构体里面也是支持索引器
     * 
     * **/

}
```

## Lesson27_静态成员

```c#
using System;

namespace Lesson27_静态成员
{

    #region  知识点一 静态成员基本概念

    //静态关键字 static
    //用static修饰的 成员变量 方法 属性等
    //称为静态成员

    //静态成员的特点是 直接用类名点出使用

    #endregion

    #region 知识点二 早已出现的静态成员

    #endregion

    #region 知识点三 自定义静态成员

    class Test
    {
        public static float PI = 3.1415926f;

        public int testInt = 1;

        //静态成员方法
        public static float CalcCircle(float r)
        {
            #region 知识点六 静态函数中不能使用非静态成员

            //成员变量只能将对象实例化出来后 才能点出来使用 不能无中生有
            //不能直接使用 非静态成员 否则会报错

            #endregion



            return PI * r * r;
        }

        //成员方法
        public void TestFun()
        {
            Console.WriteLine("Hello Wrold!");
        }

    }

    #endregion

    #region 知识点五 为什么可以直接点出来使用

    /*
     * 程序是不能无中生有的
     * 我们要使用的对象 变量 函数都是要在内存中分配内存空间的
     * 之所以要实例化对象 目的就是分配内存空间 在程序中产生一个抽象的对象
     * **/

    /*
     * 静态成员的特点
     * 程序开始运行时 就会分配内存空间 所以我们就能直接使用
     * 静态成员和程序同生共死
     * 只要使用了它 直到程序结束时内存空间才会被释放
     * 所以一个静态成员就会有自己唯一的一个“内存小房间”
     * 这让静态成员就有了唯一性
     * 在任何地方使用都是用的小房间里的内容 改变了它也是改变小房间里的内容
     * **/

    #endregion


    #region 知识点七 非静态函数可以使用静态成员



    #endregion

    #region 知识点八 静态成员对于我们的作用

    /*
     * 静态变量：
     * 1.常用唯一变量的声明
     * 2.方便别人获取的对象声明
     * 静态方法：
     * 常用的唯一的方法声明 比如 相同规则的数学计算相关函数
     * **/

    #endregion

    #region 知识点九 常量和静态变量

    /*
     * const(常量) 可以理解为特殊的static
     * 相同点
     * 他们都可以通过类名点出使用
     * 不同点
     * 1.const必须初始化，不能修改 static没有这个规则
     * 2.const只能修饰变量 static可以修饰很多
     * 3.const一定是写在访问修饰符后面的 static没有这个要求
     * **/

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("静态成员");

            #region 知识点四 静态成员的使用

            Console.WriteLine(Test.PI);

            Console.WriteLine(Test.CalcCircle(2));

            Test t = new Test();
            Console.WriteLine(t.testInt);
            t.TestFun();
            #endregion

        }
    }

    //总结：
    /*
     * 概念：用static修饰的成员变量 成员方法 成员属性等 就称为静态成员
     * 特点：直接用类名点出来使用
     * 生命周期 ： 和程序同生共死
     * 程序运行后就会一直存在内存中 直到程序结束后才会释放 因此静态成员具有唯一性
     * 
     * 注意：
     * 1.静态函数中不能直接使用非静态成员
     * 2.非静态函数中可以直接使用静态成员
     * **/

    //常量和静态变量
    //常量是特殊的静态变量
    /*
     * 相同点
     * 他们都可以通过类名点出来使用
     * 不同点
     * 1.const必须初始化不能被修改 static没有这个规则
     * 2.const只能修饰变量 static可以修饰很多
     * 3.const不能写在访问修饰符前面 一定是写在变量声明前面 static没有这个规则
     * **/
}
```

## Lesson28_静态类和静态构造函数

```c#
using System;

namespace Lesson28_静态类和静态构造函数
{

    #region 知识点一 静态类

    //概念
    //有static修饰的类

    //特点
    //只能包含静态成员
    //不能被实例化

    //作用
    //1.将常用的静态成员写在静态类中 方便使用
    //2.静态类不能被实例化 更能体现工具类的 唯一性
    //比如 Console就是一个静态类

    #endregion

    static class TestStatic
    {
        //静态成员变量
        public static int testIndex = 0;

        public static void TestFun()
        {

        }

        public static int TestIndex 
        {
            get;
            set;
        }
    }

    #region 知识点二 静态构造函数

    //概念
    //在构造函数加上 static 修饰

    //特点
    /*  1.静态类和普通类都可以有
     *  2.不能使用访问修饰符
     *  3.不能有参数
     *  4.只会自动调用一次
     * 
     * **/

    //作用
    //在静态构造函数中初始化 静态变量

    //使用
    //1.在静态类中的静态构造函数
    static class StaticClass
    {
        public static int testInt = 100;
        public static int testInt2 = 200;

        static StaticClass()
        {
            Console.WriteLine("静态构造函数调用");
        }
    }

    //2.普通类中的静态构造函数

    class Test
    {
        public static int testInt = 200;
        static Test()
        {
            Console.WriteLine("普通类的静态构造函数");
        }

        public Test()
        {
            Console.WriteLine("成员函数");
        }
    }

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("静态类和静态构造函数");

            Console.WriteLine(StaticClass.testInt);
            Console.WriteLine(StaticClass.testInt2);
            Console.WriteLine(Test.testInt);

            Test t = new Test();
            Test t2 = new Test();

           // Console.WriteLine(StaticClass.TestStatic());

        }
    }

    /*
     * 总结：
     * 静态类
     * 用static 修饰的类
     * 特点 
     * 只能包含静态成员
     * 不能实例化
     * 作用
     * 工具类
     * 拓展方法
     * **/

    /*
     * 静态构造函数
     * 用static 修饰的构造函数
     * 特点 
     * 静态类和普通类都可以有静态构造函数
     * 不能使用访问修饰符
     * 不能有参数
     * 只会自动调用一次
     * 作用
     * 初始化静态成员
     * **/

}
```

![image-20221105212709949](https://cdn.jsdelivr.net/gh/PopuDiver/Typora-MapDepot/Typora-MapDepot202211091922974.png)

## Lesson29_拓展方法

```c#
using System;

namespace Lesson29_拓展方法
{

    #region 知识点一 拓展方法基本概念

    /*
     * 概念
     * 为现有的非静态 变量类型 添加新方法
     * 作用 
     * 1.提升程序拓展性
     * 2.不需要在对象中重新写方法
     * 3.不需要继承来添加方法
     * 4.为别人封装的类型写额外的方法
     * 
     * 特点：
     * 1.一定是写在静态类中
     * 2.一定是个静态函数
     * 3.第一个参数为拓展目标
     * 4.第一个参数用this修饰
     * **/

    #endregion

    #region 知识点二 基本语法
    //访问修饰符 static 返回值 函数名(this 拓展类名 参数名，参数类型 参数名 ， 参数类型 参数名.......)
    #endregion

    #region 知识点三 实现

    static class Tools
    {
        //为int拓展了一个成员方法
        //成员方法是需要实例化对象之后才能使用的
        public static void SpeakValue(this int value)
        {
            //拓展方法的逻辑
            Console.WriteLine("拓展的方法" + value);
        }

        public static void Fun2(this Test t,int j)
        {
            j = 10;
            Console.WriteLine("为Test拓展的方法" + j);
        }

    }

    #endregion

    #region 知识点五 为自定义的类型拓展方法

    class Test
    {
        public int i = 10;
        public void Fun1()
        {
            Console.WriteLine("123");
        }

        public void Fun2()
        {
            Console.WriteLine("456");
        }
    }

    //如果拓展方法和自身方法同名且同参，那会默认调用自身的方法，拓展方法相当于无用
    //但是如果拓展方法 参数不同，可以视为重载，会根据调用者调用时传入的参数来进行选择使用哪个方法

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("拓展方法");

            #region 知识点四 使用

            int i = 10;
            i.SpeakValue();

            Test t = new Test();
            t.Fun2();

            #endregion

        }
    }

    /*
     * 总结：
     * 概念：为现有的非静态的 变量类型 添加方法
     * 作用 
     * 提升程序拓展性
     * 不需要在对象中重新写方法
     * 不需要继承来添加方法
     * 为别人封装的方法写额外的方法
     * 
     * 特点：
     * 静态类中的静态方法
     * 第一个参数代表拓展的目标
     * 第一个参数前面一定要加this
     * 
     * 可以有返回值 和 n个参数
     * 根据需求而定
     * **/

}
```

## Lesson30_封装__运算符重载

```c#
using System;

namespace Lesson30_封装_运算符重载
{

    #region 知识点一 基本概念

    //概念
    //让自定义类和结构体 能够使用运算符

    //使用关键字 operator

    //特点
    //1.一定是一个公共的静态方法
    //2.返回值写在operator前
    //3.逻辑处理自定义

    //作用
    //让自定义类和结构体对象可以进行运算
    //注意
    //1.条件运算符需要成对实现
    //2.一个符号可以多个重载
    //3.不能使用ref和out方法

    #endregion

    #region 知识点二 基本语法
    //public static 返回类型 operator 运算符(参数列表)
    #endregion

    #region 知识点三 实例

    class Point
    {
        public int x;
        public int y;

        public static Point operator +(Point p1,Point p2)
        {
            Point p = new Point();
            p.x = p1.x + p2.x;
            p.y = p1.y + p2.y;
            return p;
        }

        public static Point operator +(Point p1, int value)
        {
            Point p = new Point();
            p.x = p1.x + value;
            p.y = p1.y + value;
            return p;
        }
    }

    #endregion

    #region 知识点五 可重载和不可重载的运算符

    #region 可重载的运算符

    #region 算数运算符

    // + - * / % ++ -- 都可以进行重载

    #endregion

    #region 逻辑运算符

    // ！可以进行重载
    //注意参数个数

    #endregion

    #region 位运算符

    // & | ^ ~ << >> 都可以进行重载
    //注意参数个数

    #endregion

    #region 条件运算符

    //1.返回值一般是bool值 也可以是其他的
    //2.相关符号必须配对实现

    #endregion

    #endregion

    #region 不可重载的运算符

    //逻辑与(&&) 逻辑或(||)
    //索引符[]
    //强转运算符()
    //特殊运算符
    //点运算 三目运算符 赋值符号

    #endregion

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("封装_运算符重载");

            #region 知识点四 使用

            Point p = new Point();
            p.x = 1;
            p.y = 1;
            Point p2 = new Point();
            p2.x = 2;
            p2.y = 2;

            Point p3 = p + p2;
            Point p4 = p3 + 2;
            Point p5 = p2 + p3;
            Console.WriteLine("{0}sdasda{1}",p.x, p.y);

            #endregion
        }
    }

    /*
     * 总结
     * 关键
     * operator
     * 固定语法
     * public static 返回值 operator 运算符(参数列表)
     * 作用：
     * 让自己定义类或者结构体对象 进行运算
     * 
     * 注意 
     * 1.参数的数量需要注意
     * 2.条件运算符的配对实现
     * 3.一个符号可以多个重载
     * 4.不能使用 ref 和 out 
     * **/

}
```

## Lesson31_内部类和分部类

```c#
using System;

namespace Lesson31_内部类和分部类
{

    #region 知识点一 内部类

    //概念 
    //在一个类中再声明一个类

    //特点
    //使用时 要用包裹者点出自己

    //作用
    //亲密关系的变现

    //注意
    //访问修饰符作用很大

    class Person
    {
        public int age;
        public string name;
        public Body body;

        public class Body
        {
            Arm leftArm;
            Arm rightArm;
            class Arm
            {

            }
        }
    }

    #endregion

    #region 知识点二 分部类

    //概念
    //把一个类分成几部分声明

    //关键字
    //partial

    //作用
    //分部描述一个类
    //增加程序的拓展性

    //注意
    //分部类可以写在多个脚本文件中
    //分部类的访问修饰符 要一致
    //分部类中不能有重复成员

    partial class Student
    {
        public bool sex;
        public string name;
    }

    partial class Student
    {
        public int number;
        public void Speak(string str)
        {
            Console.WriteLine(str);
        }
    }

    #endregion

    #region 知识点三 分部方法

    /*
     * 概念
     * 将方法的声明和实现分离
     * 特点
     * 1.不能加访问修饰符 默认私有
     * 2.只能在分部类中声明
     * 3.返回值只能是 void
     * 4.可以有参数但不用out关键字
     * 
     * 局限性比较大
     * **/

    //可以将一个类的方法分开写，一个声明一个实现，但是方法名和访问修饰符 返回值必须一致

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("内部类和分部类");

            Person p = new Person();

            Person.Body body = new Person.Body();

            Student s = new Student();
            s.number = 10;
            Console.WriteLine(s.number);
            s.Speak("Hello World!");
        }
    }
}
```

## Lesson32_继承__继承的基本规则

```c#
using System;

namespace Lesson32_继承_继承的基本规则
{

    #region 知识点一 基本概念

    /*
     * 一个类A继承一个类B
     * 类A将会继承类B的所有成员
     * A类将拥有B类的所有特征和行为
     * 
     * 被继承的类
     * 称为 父类 基类 超类
     * 
     * 继承的类
     * 称为子类 派生类
     * 
     * 子类可以有自己的特征和行为
     * 
     * 特点
     * 单根性 子类只能有一个父类
     * 传递性 子类可以间接继承父类的父类
     * **/

    #endregion

    #region 知识点二 基本语法

    //class 类名: 被继承的类名{}

    #endregion

    #region 知识点三 实例

    class Teacher
    {
        //名字
        public string name;
        //职工号
        public int number;
        //介绍名字
        public void SpeakName()
        {
            Console.WriteLine(name);
        }

    }

    class TeachingTeacher : Teacher
    {
        //教学科目
        public string subject;
        public void SpeakSubject()
        {
            Console.WriteLine(subject + "老师");
        }
    }

    class ChineseTeacher : TeachingTeacher
    {
        public void Skill()
        {
            Console.WriteLine("彼方尚有荣光在，少年不惧岁月长");
        }
    }

    #endregion

    #region 知识点四 访问修饰符的影响

    /*public - 公共 内外部访问
     * private - 私有 内部访问
     * protected - 保护 内部和子类访问
     * **/

    /*internal - 内部的 只有在同一个程序集的文件中 内部类型或者是成员才可以访问
     * **/

    #endregion

    #region 知识点五 子类和父类的同名成员

    /*
     * 概念
     * C#中允许子类存在和父类同名的成员
     * 但是极不建议使用
     * **/

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("继承_继承的基本规则");

            TeachingTeacher teachingTeacher = new TeachingTeacher();
            teachingTeacher.name = "HW";
            teachingTeacher.number = 123;
            teachingTeacher.SpeakName();
            teachingTeacher.subject = "Russian";
            teachingTeacher.SpeakSubject();

            ChineseTeacher ct = new ChineseTeacher();
            ct.number = 123;
            ct.name = "语文老师";
            ct.subject = "语文";
            ct.SpeakName();
            ct.SpeakSubject();
            ct.Skill();

        }
    }

    /*
     * 总结
     * 继承基本语法
     * class 类名：父类名
     * 1.单根性 ： 只能继承一个父类
     * 2.传递性 ： 子类可以继承父类的父类 的所有内容
     * 3. 访问修饰符 对于成员的影响
     * 
     * 4.不建议使用 在子类中声明和父类同名的成员
     * **/

}
```

## Lesson33_里氏替换原则

```c#
using System;

namespace Lesson33_里氏替换原则
{

    #region 知识点一 基本概念

    /*
     * 里氏替换原则是面向对象七大原则中最重要的原则
     * 概念：
     * 任何父类出现的地方 子类都可以替代
     * 重点
     * 语法表现 --- 父类容器装子类对象 因为子类对象包含了父类的所有内容
     * 作用：
     * 方便进行对象存储和管理
     * **/

    #endregion

    #region 知识点二 基本实现

    class GameObject 
    {


    }

    class Player : GameObject
    {
        public void PlayerAtk()
        {
            Console.WriteLine("玩家攻击");
        }
    }

    class Monster : GameObject
    {
        public void MonsterAtk()
        {
            Console.WriteLine("怪物攻击");
        }
    }

    class Boss : GameObject
    {
        public void BossAtk()
        {
            Console.WriteLine("Boss攻击");
        }
    }

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("继承 里氏替换原则");

            //里氏替换原则 用父类容器 装载子类对象
            GameObject player = new Player();
            GameObject monster = new Monster();
            GameObject boss = new Boss();

            GameObject[] objects = new GameObject[] { new Player(), new Monster(), new Boss() };

            #region 知识点三 is 和 as

            /*
             * 基本概念
             * is 判断一个对象 是否是执行类对象
             * 返回值 bool 是为真 不是为假
             * as 将一个对象转换为指定类对象
             * 返回值 指定类型对象
             * 成功返回执行类型对象 失败返回null
             * **/

            //Player p = monster as Player;

            //if(player is Player)
            //{

            //}else if(player is Monster)
            //{

            //}

            if (player is Player)
            {
                Player p = player as Player;
                p.PlayerAtk();

                (player as Player).PlayerAtk();

            }

            for(int i = 0;i < objects.Length; i++)
            {
                if(objects[i] is Player)
                {
                    (objects[i] as Player).PlayerAtk();
                }else if (objects[i] is Monster)
                {
                    (objects[i] as Monster).MonsterAtk();
                }else if(objects[i] is Boss)
                {
                    (objects[i] as Boss).BossAtk();
                }
            }

            /*
             * 基本语法
             * 类对象 is 类名 该语句块 会有一个bool 返回值 true 和 false
             * 类对象 as 类名 该语句块 会有一个对象返回值 对象和 null
             * **/

            #endregion

        }
    }

    /*
     * 总结
     * 概念：父类容器装子类对象
     * 作用：方便进行对象的存储和管理
     * 使用：is 和 as
     * is 用于判断
     * as 用于转换
     * 注意 不能用子类容器装父类对象
     * **/

}
```

## Lesson34_继承__继承中的构造函数

```c#
using System;

namespace Lesson34_继承_继承中的构造函数
{

    #region 知识点一 继承中的构造函数 基本概念

    //特点
    //当声明一个子类对象时
    //先执行父类的构造函数
    //再执行子类的构造函数

    //注意：
    //1.父类的无参构造 很重要
    //2.子类可以通过base关键字 代表父类 调用父类构造

    #endregion

    #region 知识点二 继承中构造函数的执行顺序
    //父类的父类的构造->.......父类构造-> ...... -> 子类构造
    #endregion

    #region 知识点三 父类的无参构造函数

    /*
     * 如果父类使用的默认的无参构造 不会有影响
     * 如果父类声明了有参的构造函数 那么会报错 因为父类的无参构造函数已经被顶掉
     * **/

    #endregion

    #region 知识点四 通过base调用指定父类构造

    class Father
    {
        public Father(int i)
        {
            Console.WriteLine("父类有参构造");
        }
    }

    class Son : Father
    {
        public Son(int i) : base(i)
        {
            Console.WriteLine("Son一个参数的构造");
        }

        public Son(int i,string str) : this(i)
        {
            Console.WriteLine("Son的两个参数的构造");
        }
    }

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("继承_继承中的构造函数");

            Son s = new Son(1,"a");
        }
    }

    /*
     * 总结：
     * 继承中的构造函数 
     * 特点 
     * 执行顺序 是先执行父类的构造函数 再执行子类的 从老祖宗开始 依次一代一代向下执行
     * 
     * 父类中的无参构造函数 很重要
     * 如果被顶掉 子类中就无法默认调用无参构造了
     * 解决方法：
     * 1.始终保持声明一个无参构造
     * 2.通过base关键字 调用指定父类的构造
     * 注意 
     * 了解this和base的区别
     * **/

}
```

## Lesson35_封装__万物之父和装箱拆箱

```c#
using System;

namespace Lesson35_封装_万物之父和装箱拆箱
{

    class Father
    {
        public Father()
        {
            Console.WriteLine("父类的无参构造");
        }
    }

    class Son : Father
    {
        public Son()
        {
            Console.WriteLine("子类的无参构造");
        }

        public void Speak()
        {
            Console.WriteLine("子类成员函数");
        }

    }


    #region 知识点一 万物之父

    /*
     * 万物之父
     * 关键字 object
     * 概念：
     * object 是所有类型的基类 他是一个类(引用类型)
     * 作用：
     * 1.可以利用里氏替换原则 用object容器装所有对象
     * 2.可以用来表示不确定类型 作为函数参数类型
     * **/

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");

            #region 知识点二 万物之父的使用

            //引用类型
            object o = new Son();

            //用is 和 as 来判断和转换即可
            if (o is Son)
            {
                (o as Son).Speak();
            }
            //值类型
            object o2 = 1;
            //用强转
            float f1 = (float)o2;
            //特殊的string类型
            object str = "123456";
            string str2 = str.ToString();
            str2 = str as string;

            int[] arr = new int[10];
            object arr1 = new int[10];
            int[] ar = (int[])arr;
            ar = arr1 as int[];

            #endregion

            #region 知识点三 装箱拆箱

            /*
             * 发生条件
             * 用object存储值类型(装箱)
             * 再把object转为值类型(拆箱)
             * 
             * 装箱
             * 把值类型用引用类型存储
             * 栈内存会迁移到堆内存中
             * 
             * 拆箱
             * 把引用类型存储的值类型取出来
             * 堆内存会迁移到栈内存中
             * 
             * 好处 不确定类型时 可以方便参数的存储和传递
             * 坏处 存在内存迁移 增加性能消耗
             * **/

            //装箱
            object v = 3;
            int intValue = (int)v;
            #endregion

            TestFun(0, ar, new Son());

        }

        static void TestFun(params object[] array)
        {

        }
    }

    /*
     * 总结
     * 万物之父 object
     * 基于里氏转换原则 可以用object 容器装载一切类型的变量
     * 它是所有类型的基类
     * 
     * 装箱拆箱
     * 用object存值类型(装箱)
     * 把object里面存的值 转换出来(拆箱)
     * 好处
     * 不确定类型时 可以用object 方便存储和传递
     * 坏处
     * 存在内存的迁徙 增加了性能消耗
     * 尽量少用
     * **/

}
```

## Lesson36_多态__vob

```c#
using System;

namespace Lesson36_多态_vob
{

    #region 知识点一 多态的概念

    /*
     * 多态按字面意思就是多种状态
     * 让继承同一父类的子类们 在执行相同方法时 有不同的表现(状态)
     * 主要目的
     * 同一父类的对象 执行相同的行为 (方法) 有不同的表现
     * 解决的问题 
     * 让同一个对象有唯一行为的特征
     * **/

    #endregion

    #region 知识点二 解决的问题

    class Father
    {
        public void SpeakName()
        {
            Console.WriteLine("父类的方法");
        }
    }

    class Son : Father
    {
        public new void SpeakName()
        {
            Console.WriteLine("子类的方法");
        }
    }

    #endregion

    #region 知识点三 多态的实现

    /*
     * 编译时多态 -- 函数重载 开始就写好的
     * 
     * 运行时多态( vob 抽象函数 接口 )
     * v ： virtual
     * o ： override(重写)
     * b ： base(父类)
     * **/

    class GameObject
    {
        public string name;
        public GameObject(string name)
        {
            this.name = name;
        }

        //虚函数 可以被子类重写
        public virtual void Atk()
        {
            Console.WriteLine("游戏对象进行攻击");
        }
    }

    class Player : GameObject
    {
        public Player(string name) : base(name)
        {
            //Console.WriteLine("玩家进行行动");
        }

        public override void Atk()
        {
            //base的作用
            //代表父类 可以通过base来保留父类的行为
            //base.Atk();
            base.Atk();
            Console.WriteLine("玩家进行行动");
        }
    }

    class Monster : GameObject
    {
        public Monster(string name) : base(name)
        {

        }

        public override void Atk()
        {
            base.Atk();
            Console.WriteLine("Monster进行攻击");
        }
    }

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("多态_vob");

            Father f = new Son();
            f.SpeakName();

            (f as Son).SpeakName();

            GameObject p = new Player("HW");
            p.Atk();

            GameObject m = new Monster("原神");
            m.Atk();

        }
    }

    //总结：
    //多态 让同一类型的对象 执行相同行为时有不同的表现
    //解决的问题 让同一对象有唯一的行为特征
    //vob ： virtual override base 
    // v和o一定是结合使用的 来实现多态 base 是看情况使用
}
```

## Lesson37_多态__抽象类和抽象方法

```c#
using System;

namespace Lesson37_多态_抽象类和抽象方法
{
    #region 知识点一 抽象类
    /*
     * 概念
     * 将抽象关键字abstract修饰的类
     * 特点 
     * 1.不能被实例化的类
     * 2.可以包含抽象方法
     * 3.继承抽象类必须重写其抽象方法
     * **/

    abstract class Thing
    {
        //抽象类中 封装的所有知识点都可以在其中书写
        public string name;

        //可以在抽象类中写抽象函数
    }

    class Water : Thing
    {

    }

    #endregion

    #region 知识点二 抽象函数

    //又叫纯虚方法
    //用 abstract 关键字 修饰的方法
    //特点：
    //1.只能在抽象类中声明 
    //2.没有方法体
    //3.不能是私有的
    //4.继承后必须实现 用override重写

    abstract class Fruits
    {
        public string name;

        //抽象方法 是一定不能有函数体的
        public abstract void Bad();

        public virtual void Test()
        {
            //可以选择是否写逻辑
        }
    }

    class Apple : Fruits
    {
        public override void Bad()
        {
            
        }
        //虚方法是可以由我们子类选择性实现的
        //抽象方法必须要实现
    }

    class SuperApple : Apple
    {
        //虚方法和抽象方法 都可以被子类无限重写
        public override void Bad()
        {
            base.Bad();
        }
    }

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("多态_抽象类和抽象方法");
            //抽象类不可以被实例化 但是遵循里氏替换原则
            Thing t = new Water();

        }
    }

    //总结
    //抽象类 被abstract修饰的类 不能被实例化 可以包含抽象方法
    //抽象方法 没有方法体的纯虚方法 继承后必须去实现的方法

    //注意 
    //如何选择普通类还是抽象类
    //不希望被实例化的对象 相对比较抽象的类可以使用抽象类
    //父类中的行为不太需要被实现的 只希望子类去定义具体的规则的 可以选择 抽象类然后使用其中的抽象方法来定义规则
    //作用
    //整体框架设计时 会使用

}
```

## Lesson38_多态__接口

```c#
using System;

namespace Lesson38_多态_接口
{

    #region 知识点一 接口的概念

    /*
     * 接口是行为的抽象规范
     * 它也是一种自定义类型
     * 关键字 interface
     * 
     * 接口声明 的规范
     * 1.不包含成员变量
     * 2.只包含方法 属性 索引器 事件
     * 3.成员不能被实现
     * 4.成员可以不用写访问修饰符 不能是私有的
     * 5.接口不能继承类 但是可以继承另一个接口
     * 
     * 接口的使用规范
     * 1.类可以继承多个接口 
     * 2.类继承接口后 必须实现接口中所有成员
     * 
     * 特点
     * 1.它的声明和类类似
     * 2.接口是用来继承的
     * 3.接口不能被实例化 但是可以作为容器存储对象
     * **/

    #endregion

    #region 知识点二 接口的声明

    /*
     * 接口关键字 interface
     * 语法：
     * interface 接口名
     * {
     * }
     * 一句话记忆 接口是抽象行为的基类
     * 接口命名规范 帕斯卡前面加个I
     * **/

    interface IFly
    {
        void Fly();

        string Name
        {
            get;
            set;
        }

        int this[int index]
        {
            get;
            set;
        }

        event Action doSomething;

    }

    #endregion

    #region 知识点三 接口的使用
    class Animal
    {

    }
    class Person : Animal, IFly
    {
        public event Action doSomething;

        public void Fly()
        {

        }

        public string Name
        {
            get;
            set;
        }
        
        public int this[int index]
        {
            get { return 0; }
            set { }
        }
    }

    /*
     * 接口用来继承
     * 1.类可以继承1个类 n个接口
     * 2.继承了接口后 必须实现其中的内容 并且必须是public的
     * 3.实现的接口函数 可以加virtual再在子类重写
     * 4.接口也是遵循里氏替换原则
     * **/

    #endregion

    #region 知识点四 接口可以继承接口

    //接口继承接口时 不需要实现
    //待类继承接口后 类自己去实现所有内容
    interface IWalk
    {
        void Walk();
    }

    interface IMove : IFly, IWalk
    {

    }

    class Test : IMove
    {
        public int this[int index] { get => throw new NotImplementedException(); set => throw new NotImplementedException(); }

        public string Name { get => throw new NotImplementedException(); set => throw new NotImplementedException(); }

        public event Action doSomething;

        public void Fly()
        {
            throw new NotImplementedException();
        }

        public void Walk()
        {
            throw new NotImplementedException();
        }
    }

    #endregion

    #region 知识点五 显示实现接口

    /*
     * 当一个类继承两个接口
     * 但是接口中存在着同名方法时
     * 注意 显示实现接口时 不能写访问修饰符
     * **/

    interface IAtk
    {
        void Atk();
    }
    interface ISuperAtk
    {
        void Atk();
    }

    class Player : IAtk, ISuperAtk
    {
        //显示实现接口 就是用 接口名.行为名 去实现
        void IAtk.Atk()
        {
            
        }
        void ISuperAtk.Atk()
        {

        }
    }

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("多态_接口");
            IFly f = new Person();
            IMove im = new Test();

            Player p = new Player();
            (p as IAtk).Atk();

        }
    }

    //总结 
    //继承类 是对象间的继承 包括特征行为等等
    //继承接口 是行为间的继承 继承接口的行为规范 按照规范去实现内容 
    //由于接口也是遵循里氏替换原则 所以可以用接口容器装对象
    //那么就可以实现 装载各种毫无关系但是却有相同行为的对象

    //注意
    //1.接口值包含 成员方法 属性 索引器 事件 并且都不实现 都没有访问修饰符
    //2.可以继承多个接口 但是只能继承一个类
    //3.接口可以继承接口 相当于在进行行为合并 待子类继承时再去实现具体的行为
    //4.接口可以被显示实现 主要用于实现不同接口中的同名函数的不同表现
    //5.实现的接口方法 可以加 virtual 关键字 之后子类 再重写

}
```

## Lesson39_多态__密封方法

```c#
using System;

namespace Lesson39_多态_密封方法
{

    #region 知识点一 密封方法基本概念

    /*
     * 用密封方法关键字 sealed 修饰的重写函数
     * 作用： 让虚函数或者抽象方法之后不能再被重写
     * 特点： 和override一起出现
     * **/

    #endregion

    #region 知识点二 实例

    abstract class Animal
    {
        public string name;
        public abstract void Eat();
        public virtual void Speak()
        {
            Console.WriteLine("叫");
        }
    }

    class Person : Animal
    {
        public override void Eat()
        {
            throw new NotImplementedException();
        }

        public override void Speak()
        {
            base.Speak();
        }
    }

    class WhitePerson : Person
    {
        public override void Eat()
        {
            base.Eat();
        }

        public override void Speak()
        {
            base.Speak();
        }
        
        //格式为：
        public sealed override void Speak(){
            
        }
        //密封之后不能再被重写，相当于不允许有子类
        
    }

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("多态_密封方法");
        }
    }

    //总结
    //密封方法可以让虚方法和抽象方法不能再被子类重写
    //特点 一定要和override一起成对出现

}
```

## Lesson40_命名空间

```c#
using System;

#region 知识点一 命名空间基本概念

/*
 * 概念
 * 命名空间是用来组织和重用代码的
 * 作用
 * 就像是一个工具包 类就像是一件一件的工具 都是声明在命名空间中的
 * **/

#endregion

#region 知识点二 命名空间的使用

/*
 * 基本语法
 * namespace 命名空间名
 * {
 *  类
 *  类
 * }
 * 
 * 
 * **/

namespace MyGame
{
    class GameObject
    {

    }
}

namespace MyGame
{
    class Player : GameObject
    {

    }
}

#endregion

#region 知识点三 不同命名空间中相互使用 需要引用命名空间或指明出处

//using MyGame;
//或者
//MyGame.GameObject();


#endregion

#region 知识点四 不同命名空间中允许有同名类

#endregion

#region 知识点五 命名空间可以包裹命名空间

namespace MyGame2
{
    namespace UI
    {

    }

    namespace Enemy
    {

    }
}

#endregion

#region 知识点六 关于修饰类的访问修饰符

/*
 * public -- 命名空间中的类 默认为 public
 * internal -- 只能在该程序集中使用 内部类
 * abstract -- 抽象类
 * sealed -- 密封类
 * partial -- 分部类
 * **/

#endregion

namespace Lesson40_命名空间
{
    

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("命名空间");
        }
    }
}

//总结
//1.命名空间是一个工具包 用来管理类的
//2.不同命名空间中 可以有同名类
//3.不同命名空间中相互使用 需要using引用命名空间 或者指明出处
//4.命名空间可以包裹命名空间
```

## Lesson41___面向对象__相关_万物之父中的方法

```c#
using System;

namespace Lesson41_面向对象相关_万物之父中的方法
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("面向对象相关_万物之父中的方法！");

            #region 知识回顾

            /*
             * 万物之父 object
             * 所有类型的基类 是一个引用类型
             * 可以利用里氏替换原则装载一切对象
             * 存在装箱拆箱
             * **/

            #endregion

            #region 知识点一 object中的静态方法

            /*
             * 静态方法 Equals 判断两个对象是否相等
             * 最终的判断权 交给左侧对象的Equals方法
             * 不管值类型引用类型都会按照左侧对象Equals方法的规则来进行比较
             * **/

            /*
             * 静态方法ReferenceEquals
             * 比较两个对象是否是相同的引用 主要是用来比较引用类型的对象
             * 值类型对象返回值始终是false
             * **/

            #endregion

            #region 知识点二 object中的成员方法

            /*
             * 普通方法GetType
             * 该方法在反射中是非常重要的方法 
             * 该方法的主要作用就是获取对象运行时的类型Type
             * 通过Type结合反射相关知识点可以做很多关于对象的操作
             * **/

            /*
             * 普通方法MemberwiseClone
             * 该方法用于获取对象的浅拷贝对象 口语化的意思就是会返回一个新的对象
             * 但是新对象中的引用变量会和老对象中的一致
             * **/

            #endregion

            #region 知识点三 object中的虚方法

            /*
             * 虚方法Equals
             * 默认实现还是比较两者是否为同一个引用 即相当于ReferenceEquals
             * 但是微软在所有值类型的基类System.ValueType中重写了该方法 用来比较值相等
             * 我们也可以重写该方法 定义自己的比较相等的规则
             * **/

            /*
             * 虚方法GetHashCode
             * 该方法是获取对象的哈希码
             * 一种通过算法算出的 表示对象的唯一编码 不同对象哈希码有可能一样 具体值根据哈希算法决定
             * 我们可以通过重写该函数来自己定义对象的哈希码算法 正常情况下 使用的极少 
             * **/

            /*
             * 虚方法ToString
             * 该方法用于返回当前对象代表的字符串 我们可以重写它定义我们自己的对象转字符串规则
             * 该方法非常常用 当我们调用打印方法时 默认使用的就是对象的ToString方法后打印出来的内容
             * **/

            #endregion

        }
    }

    //总结
    //1.虚方法 ToString 自定义字符串转换规则
    //2.成员方法 GetType反射相关
    //3.成员方法 MemberwiseClone 浅拷贝
    //4.虚方法 Equals 自定义判断相等的规则
}
```

## Lesson42_String

```c#
using System;

namespace Lesson42_String
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("String");

            #region 知识点一 string中的位置获取

            // string方法自带索引器 可以进string 源码中看 是一个密封类 有一个返回值为char的索引器

            #endregion

            #region 知识点二 字符串拼接

            //format方法可以进行拼接

            #endregion

            #region 知识点三 正向查找字符位置

            //IndexOf方法可以正向查找字符位置 找到返回下标 找不到返回-1

            #endregion

            #region 知识点四 反向查找指定字符串位置

            //LastIndexOf方法 找到返回下标 找不到返回-1

            #endregion

            #region 知识点五 移除指定位置后的字符
            //ReMove(位置) 从位置往后所有的字符全部移除 但是返回一个新的字符串 不会原地删除

            //ReMove(位置1，位置2) 从参数一的位置开始移除 直到参数二的位置
            #endregion

            #region 知识点六 替换指定字符串

            //Replace("字符串1","字符串2") 用字符串2替换字符串1 但是同样不会原地替换 返回一个新的字符串

            #endregion

            #region 知识点七 大小写转换

            //ToUpper 同样是不会改变原字符串 返回一个新的字符串
            //ToLower 大写转小写

            #endregion

            #region 知识点八 字符串截取
            //截取从指定位置开始之后的字符串
            //Substring(参数-位置)

            //Substring(参数1，参数2) 参数一 是开始位置 参数二 是截取长度 但是不会主动帮助判断是否越界

            #endregion

            #region 知识点九 字符串切割

            string str = "1_1|2_2|3_3|4_4|5_6|7_8|9";
            string[] strs = str.Split('|');
            for (int i = 0; i < strs.Length; i++)
            {
                Console.WriteLine(strs[i]);
            }

            #endregion

        }
    }
}
```

![image-20221108104045202](https://cdn.jsdelivr.net/gh/PopuDiver/Typora-MapDepot/Typora-MapDepot202211091922071.png)

## Lesson43___面向对象__相关_StringBuilder

```c#
using System;
using System.Text;

namespace Lesson43_面向对象相关_StringBuilder
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("面向对象相关_StringBuilder");

            #region 知识点 StringBuilder

            /*
             * C#提供的一个用于处理字符串的公共类
             * 主要解决的问题是：
             * 修改字符串而不创建新的对象 需要频繁修改和拼接的字符串可以使用它 可以提升性能
             * 使用前 需要引用命名空间
             * **/

            #region 初始化 直接指明内容
            StringBuilder str = new StringBuilder("123456789");//可以直接加第二个参数 表示声明长度
            Console.WriteLine(str);
            #endregion

            #region 容量
            //StringBuilder 存在一个容量的问题 每次往里面增加时 会自动扩容 容量会自动乘以2
            //获得容量 
            Console.WriteLine(str.Capacity);

            //获得字符长度
            Console.WriteLine(str.Length);
            #endregion

            #region 增删改查替换
            //增
            str.Append("444");
            Console.WriteLine(str);
            Console.WriteLine(str.Capacity);
            Console.WriteLine(str.Length);

            str.AppendFormat("{0} + {1}", 100, 222);
            Console.WriteLine(str);
            Console.WriteLine(str.Capacity);
            Console.WriteLine(str.Length);

            //插入
            str.Insert(0, "asd");//参数1是位置 参数2是字符串

            //删
            str.Remove(0, 10);//从参数一到参数二的所有字符执行删除

            //str.Clear();//清空函数

            //查
            //改
            str[0] = 'a';

            //替换
            str.Replace("1","asdasdasd");//原地替换 
            Console.WriteLine(str);

            //重新赋值 StringBuilder
            str.Clear();
            str.Append("123456");
            Console.WriteLine(str);

            //判断StringBuilder 是否和某一字符串相等
            if (str.Equals("123456"))
            {
                Console.WriteLine("相等");
            }

            #endregion

            #endregion

        }
    }
}
```

## Lesson44___面向对象__相关_结构体和类的区别

```c#
using System;

namespace Lesson44_面向对象相关_结构体和类的区别
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("面向对象相关_结构体和类的区别");

            #region 区别概述

            /*
             * 结构体和类最大的区别是在存储空间上的 因为结构体是值 类是引用
             * 因此他们的存储位置一个在栈上 一个在堆上
             * **/

            /*
             * 结构体和类在使用上很类似 结构体甚至可以用面向对象的思想来形容一类对象
             * 结构体具备着面向对象思想中封装的特性 但是它不具备继承和多态的特性 因此大大减少了它的使用频率
             * 由于结构体不具备继承的特性 所以它不能够使用protected保护访问修饰符
             * **/

            #region 细节区别

            /*
             * 1.结构体是值类型 类是引用类型
             * 2.结构体存在栈中 类存在堆中
             * 3.结构体成员不能使用protected访问修饰符 而类可以
             * 4.结构体成员变量声明不能指定初始值 而类可以
             * 5.结构体不能声明无参的构造函数 而类可以
             * 6.结构体声明有参构造函数后 无参构造不会被顶掉
             * 7.结构体不能声明析构函数 而类可以
             * 8.结构体不能被继承 而类可以
             * 9.结构体需要在构造函数中初始化所有成员变量 而类随意
             * 10.结构体不能被静态static修饰(不存在静态结构体) 而类可以
             * 11.结构体不能在自己内部声明和自己一样的结构体变量 而类可以
             * **/



            #endregion

            #region 结构体的特别之处
            //结构体可以继承 接口 因为接口是行为的抽象

            #endregion

            #region 如何选择结构体和类
            //1.想要使用继承和多态时 直接淘汰结构体 比如玩家 怪物等
            //2.对象是数据集合时 优先考虑结构体 比如位置 坐标等
            //3.从值类型和引用类型赋值时的区别上去考虑 比如经常被赋值传递的对象 并且
            //改变赋值对象 原对象不想跟着变化时 就用结构体 比如坐标 向量 旋转等
            #endregion

            #endregion

        }
    }
}
```

## Lesson45_抽象类和接口的区别

```c#
using System;

namespace Lesson45_抽象类和接口的区别
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("抽象类和接口的区别");

            #region 知识回顾
            /*
             * 抽象类和抽象方法
             * abstract修饰的类和方法
             * 抽象类 不能被实例化
             * 抽象方法 只能在抽象类中声明 是个纯虚方法 必须在子类中实现
             * **/

            /*
             * 接口
             * interface 自定义类型
             * 是行为的抽象
             * 不包含成员变量 
             * 仅包含方法 属性 索引器 事件 成员都不能实现 建议不写访问修饰符 默认public
             * **/

            #endregion

            #region 知识点一 相同点
            /*
             * 1.都可以被继承
             * 2.都不能直接实例化
             * 3.都可以包含方法声明
             * 4.子类必须实现未实现的方法
             * 5.都遵循里氏替换原则
             * **/
            #endregion

            #region 知识点二 区别
            /*
             * 1.抽象类中可以有构造函数 接口中不能
             * 2.抽象类只能被单一继承 接口可以被继承多个
             * 3.抽象类中可以有成员变量 接口中不能
             * 4.抽象类中可以声明成员方法 虚方法 抽象方法 静态方法 接口中只能声明没有实现的抽象方法
             * 5.抽象类方法可以使用访问修饰符 接口中建议不写 默认public
             * **/
            #endregion

            #region 如何选择抽象类和接口
            /*
             * 表示对象的用抽象类 表示行为拓展的用接口
             * 不同对象拥有的共同行为 我们往往可以使用接口来实现
             * 比如：
             * 动物是一类对象 我们选择抽象类 而飞翔是一种行为 自然选择接口
             * **/
            #endregion
        }
    }
}
```

## Lesson46_ArrayList

```c#
using System;
using System.Collections;

namespace Lesson46_ArrayList
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("ArrayList");

            #region 知识点一 ArrayList的本质

            /*
             * ArrayList是一个C#为我们封装好的类
             * 它的本质是一个object类型的数组
             * ArrayList类帮助我们实现了很多方法
             * 比如数组的增删改查
             * **/

            #endregion

            #region 知识点二 声明
            //需要引用命名空间 using System.Collections;
            ArrayList array = new ArrayList();
            #endregion

            #region 知识点三 增删改查

            //增
            array.Add(1);
            array.Add("123");
            array.Add(true);
            array.Add(new object());
            array.Add(1);
            array.Add(true);

            ArrayList array2 = new ArrayList();
            array2.Add(123);
            //范围增加(批量增加 把另一个list容器里面的内容加到后面)
            array.AddRange(array2);

            array.Insert(1, "1234565");
            Console.WriteLine(array[1]);

            //删
            //指定移除元素 从头找 找到删
            array.Remove(1);
            //移除指定位置的元素
            array.RemoveAt(2);
            //清空
            //array.Clear();

            //查
            //得到指定位置的元素
            Console.WriteLine(array[0]);

            //查看元素是否存在
            if (array.Contains("123"))
            {
                Console.WriteLine("存在123");
            }

            //正向查找元素位置
            //找到的 返回值 是位置 找不到 返回值是-1
            int index = array.IndexOf(true);
            Console.WriteLine(index);

            //反向查找元素位置
            index = array.LastIndexOf(true);
            Console.WriteLine(index);


            //改
            Console.WriteLine(array[0]);
            array[0] = "999";
            Console.WriteLine(array[0]);

            #endregion

            #region 遍历

            //长度
            Console.WriteLine(array.Count);
            //容量
            Console.WriteLine(array.Capacity);

            for (int i = 0; i < array.Count; i++)
            {
                Console.WriteLine(array[i]);
            }

            Console.WriteLine("***********************");
            //迭代器遍历
            foreach (object item in array)
            {
                Console.WriteLine(item);
            }
            #endregion

            #region 知识点四 装箱拆箱
            /*
             * ArrayList本质上是一个可以自动扩容的object数组
             * 由于用万物之父来存储数据 自然存在装箱拆箱
             * 当往其中进行值类型存储时就是在装箱 当将值类型对象取出来转换使用时 就存在拆箱
             * 所以ArrayList尽量少用 之后我们会学习更好的数据容器
             * **/

            int i = 1;
            array[0] = i;//装箱

            i = (int)array[0];//拆箱
            #endregion

        }
    }
}
```

## Lesson47_Stack

```c#
using System;
using System.Collections;

namespace Lesson47_Stack
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Stack");

            #region 知识点一 Stack的本质
            /*
             * Stack（栈） 是一个C#为我们封装好的类
             * 它的本质也是object[]数组 只是封装了特殊的存储规则
             * **/

            /*
             * Stack是栈存储容器 栈是一种先进后出的数据结构
             * 先存入的数据后获取 后存入的数据先获取
             * 栈是先进后出
             * **/
            #endregion

            #region 知识点二 声明
            //需要引用命名空间 System.Collections
            Stack stack = new Stack();
            #endregion

            #region 知识点三 增取查改

            #region 增
            //压栈
            stack.Push(1);
            stack.Push("123");
            stack.Push(true);
            stack.Push(1.2f);
            stack.Push(new object());
            #endregion

            #region 取
            //栈中不存在删除的概念
            //只有取的概念
            //弹栈
            object v = stack.Pop();
            Console.WriteLine(v);
            #endregion

            #region 查
            //1.栈无法查看指定位置的 元素
            // 只能查看栈顶的内容
            v = stack.Peek();
            Console.WriteLine(v);

            //2.查看元素是否存在于栈中
            if (stack.Contains(1.2f))
            {
                Console.WriteLine("存在{0}",stack.Pop());
            }

            #endregion

            #region 改
            //栈无法改变其中的元素 只能压栈和弹栈
            //只能清空然后再重新压入栈
            #endregion

            #endregion

            #region 知识点四 遍历

            //1.长度
            Console.WriteLine(stack.Count);
            Console.WriteLine("-------------------");
            //2.用foreach遍历
            // 而且遍历出来的顺序 也是从栈顶到栈底
            foreach (object item in stack)
            {
                Console.WriteLine(item);
            }
            Console.WriteLine("-------------------");
            //3.还有一种遍历方式
            // 将栈转换为object数组
            //遍历出来的顺序 也是从栈顶到栈底
            object[] array = stack.ToArray();
            for (int i = 0; i < array.Length; i++)
            {
                Console.WriteLine(array[i]);
            }

            Console.WriteLine("-------------------");
            //4.循环弹栈
            while (stack.Count > 0)
            {
                object o = stack.Pop();
                Console.WriteLine(o); ;
            }
            Console.WriteLine(stack.Count);
            #endregion

            #region 知识点五 装箱拆箱
            //由于用万物之父来存储数据 自然存在装箱拆箱
            //当往其中进行值类型存储时就是在装箱
            //当将值类型对象取出来转换使用时 就存在拆箱
            #endregion
        }
    }
}
```

## Lesson48_Queue

```c#
using System;
using System.Collections;

namespace Lesson48_Queue
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Queue");

            #region 知识点一 Queue本质
            /*
             * Queue是一个C#为我们封装好的类
             * 它的本质也是object[]数组 只是封装了特殊的存储规则
             * **/

            /*
             * Queue是队列存储容器
             * 队列是一种先进先出的数据结构
             * 先存入的数据先获取 后存入的数据后获取
             * 先进先出
             * **/

            #endregion

            #region 知识点二 声明
            //需要引入命名空间 System.Collections
            Queue queue = new Queue();
            #endregion

            #region 知识点三 增取查改

            #region 增
            queue.Enqueue(1);
            queue.Enqueue("123456");
            queue.Enqueue(1.2f);
            queue.Enqueue(new object());


            #endregion

            #region 取
            //队列中不存在删除的概念
            //只有取的概念 取出先加入的对象
            object v = queue.Dequeue();
            Console.WriteLine(v);
            v = queue.Dequeue();
            Console.WriteLine(v);
            #endregion

            #region 查
            //1.查看队列头部元素但不会移除
            v = queue.Peek();
            Console.WriteLine(v);

            //2.查看元素是否存在于队列中
            if (queue.Contains("123456"))
            {
                Console.WriteLine("存在123456");
            }

            #endregion

            #region 改
            //队列无法改变其中的元素 只能进出队列
            //只能使用清空函数 Clear()
            #endregion

            #endregion

            #region 知识点四 遍历 
            //1.长度
            Console.WriteLine(queue.Count);
            //2.用foreach遍历
            foreach (object item in queue)
            {
                Console.WriteLine(item);
            }

            //3.还有一种遍历方式
            //将队列转换为object数组
            object[] array = queue.ToArray();

            for (int i = 0; i < array.Length; i++)
            {
                Console.WriteLine(array[i]);
            }

            //4.循环出列
            while(queue.Count > 0)
            {
                object o = queue.Dequeue();
                Console.WriteLine(o);
            }

            #endregion

            #region 知识点五 装箱拆箱
            //由于用万物之父来存储数据 自然存在装箱拆箱
            //当往其中进行值类型存储时就是在装箱
            //当将值类型对象取出来转换使用时 就存在拆箱
            #endregion

        }
    }
}
```

## Lesson49_HashTable

```c#
using System;
using System.Collections;

namespace Lesson49_HashTable
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("HashTable");

            #region 知识点一 HashTable的本质
            /*
             * HashTable(又称散列表) 是基于键的哈希代码组织起来的 键值对
             * 它的主要作用是提高数据查询的效率
             * 使用键来访问集合中的元素
             * **/

            #endregion

            #region 知识点二 声明
            //需要引用命名空间 System.Collections
            Hashtable hashtable = new Hashtable();
            #endregion

            #region 知识点三 增删查改

            #region 增
            hashtable.Add(1,"123");
            hashtable.Add("123", 2);
            hashtable.Add(true, false);
            hashtable.Add(false, true);
            //注意 不能出现相同的键
            #endregion

            #region 删
            //1.只能通过键去删除
            hashtable.Remove(1);
            //2.删除不存在的键 没有什么反应
            hashtable.Remove(2);
            //3.或者直接清空
            //hashtable.Clear();
            #endregion

            #region 查
            //1.通过键查看值
            //找不到会返回空
            Console.WriteLine(hashtable[1]);

            hashtable.Add(1, "123");
            //2.查看是否存在
            //根据键检测
            if (hashtable.Contains(1))
            {
                Console.WriteLine("存在1这个键");
            }
            if (hashtable.ContainsKey(1))
            {
                Console.WriteLine("存在1键值对这个键");
            }
            if (hashtable.ContainsValue("123"))
            {
                Console.WriteLine("存在1键值对这个值");
            }
            //根据值检测
            #endregion

            #region 改
            //改只能更改 键对应的值的内容 不能修改键
            #endregion

            #endregion

            #region 知识点四 遍历

            Console.WriteLine(hashtable.Count);
            //1.遍历所有键
            foreach (object item in hashtable.Keys)
            {
                Console.WriteLine("键 + " + item);
                Console.WriteLine(" 值 + " + hashtable[item]);
            }
            Console.WriteLine("------------------------------------");
            //2.遍历所有值
            foreach (object item in hashtable.Values)
            {
                Console.WriteLine("值 + " + item);
            }
            Console.WriteLine("--------------------------------------");
            //3.键值对一起遍历
            foreach (DictionaryEntry item in hashtable)
            {
                Console.WriteLine("键 + " + item.Key + " 值 + " + item.Value);
            }
            Console.WriteLine("--------------------------------------");
            //4.迭代器遍历法
            IDictionaryEnumerator myEnumerator = hashtable.GetEnumerator();
            bool flag = myEnumerator.MoveNext();
            while (flag)
            {
                Console.WriteLine("键 + " + myEnumerator.Key + " 值 + " + myEnumerator.Value);
                flag = myEnumerator.MoveNext();
            }
            #endregion

            #region 知识点五 装箱拆箱
            //由于用万物之父来存储数据 自然存在装箱拆箱
            //当往其中进行值类型存储时就是在装箱
            //当将值类型对象取出来转换使用时 就存在拆箱
            #endregion

        }
    }
 }
```

## Lesson50_泛型

```c#
using System;

namespace Lesson50_泛型
{

    #region 知识点一 泛型是什么
    /*
     * 泛型实现了类型参数化 达到代码重用目的
     * 通过类型参数化 来实现同一份代码上操作多种类型
     * 
     * **/

    /*
     * 泛型相当于类型占位符
     * 定义类或方法时使用替代副代表变量类型
     * 当真正使用类或者方法时再具体指定类型
     * **/
    #endregion

    #region 知识点二 泛型分类
    /*
     * 泛型类和泛型接口
     * 基本语法：
     * class 类名<泛型占位字母>
     * interface 接口名<泛型占位字母>
     * **/

    //泛型函数
    //基本语法：函数名<泛型占位字母>(参数列表)

    //注意 泛型占位字母可以有多个 用逗号分开
    #endregion

    #region 知识点三 泛型类和接口
    class TestClass<T>
    {
        public T value;
    }

    class TestClass2<T1, T2, T3>
    {
        public T1 value1;
        public T2 value2;
        public T3 value3;
    }

    interface TestInterface<T>
    {
        T value
        {
            get;
            set;
        }
    }

    class Test : TestInterface<int>
    {
        public int value { get => throw new NotImplementedException(); set => throw new NotImplementedException(); }
    }
    #endregion

    #region 知识点四 泛型方法

    //1.普通类中的泛型方法
    class Test2
    {
        public void TestFun<T>(T value)
        {
            Console.WriteLine(value);
        }
        public void TestFun<T>()
        {
            //用泛型类型 在里面做一些逻辑处理
            T t = default(T);
        }
        public T TestFun<T>(string v)
        {
            return default(T);
        }

    }

    //2.泛型类中的泛型方法
    class Test2<T>
    {
        public T value;

        public void TestFun1<T>(T t)
        {

        }

        //这个不是泛型方法 因为T是泛型类声明的时候确定的 所以不叫泛型方法 我们不能去动态变化了
        public void TestFun(T t)
        {

        }
    }

    #endregion

    #region 知识点五 泛型的作用
    /*
     * 1.不同类型对象的相同逻辑处理就可以选择泛型
     * 2.使用泛型可以一定程度避免装箱拆箱
     * 可以用来优化ArrayList
     * **/
    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("泛型");

            TestClass<int> t = new TestClass<int>();
            t.value = 10;
            Console.WriteLine(t.value);

            TestClass2<int, string, bool> t2 = new TestClass2<int, string, bool>();
            Test2 tt = new Test2();
            tt.TestFun<string>("123456");
        }
    }

    /*
     * 总结：
     * 1.声明泛型时 它只是一个类型的占位符
     * 2.泛型真正起作用的时候 是在使用它的时候
     * 3.泛型占位字母可以有n个用逗号分开
     * 4.泛型占位字母一般是大写字母
     * 5.不确定泛型类型时 获取默认值 可以使用 default (占位字符)
     * 6.看到<>包裹的字母 那肯定是泛型
     * **/
}
```

## Lesson51_泛型约束

```c#
using System;

namespace Lesson51_泛型约束
{

    #region 知识点一 什么是泛型约束
    /*
     * 让泛型的类型有一定的限制
     * 关键字 where
     * 泛型约束一共有6种
     * 1.值类型                                                where 泛型字母 ： struct
     * 2.引用类型                                              where 泛型字母 ： class
     * 3.存在无参公共构造函数                                  where 泛型字母 ： new()
     * 4.某个类本身或者其派生类                                where 泛型字母 ： 类名
     * 5.某个接口的派生类型                                    where 泛型字母 ： 接口名
     * 6.另一个泛型类型本身或者派生类型                        where 泛型字母 ： 另一个泛型字母
     * **/
    #endregion

    #region 知识点二 各泛型约束的讲解

    #region 值类型约束
    class Test1<T> where T : struct
    {
        public T value;
        public void TestFun<K>(K k) where K : struct
        {

        }
    }
    #endregion

    #region 引用类型约束
    class Test2<T> where T : class
    {
        public T value;
        public void TestFun<K>(K k)where K : class
        {

        }
            
    }
    #endregion

    #region 公共无参构造约束
    //要是一个有公共无参构造函数的非抽象类
    #endregion

    #region 类约束
    //只可以写类本身或者派生类 不可以写父类
    #endregion

    #endregion

    #region 知识点三 约束的组合使用
    class Test7<T> where T : class , new()
    {

    }
    #endregion

    #region 知识点四 多个泛型有约束
    class Test8<T,K> where T :class,new() where K : struct
    {

    }
    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("泛型约束");
        }
    }

    /*
     * 总结：
     * 泛型约束：让类型有一定限制
     * class
     * struct
     * new()
     * 类名
     * 接口名
     * 另一个泛型字母
     * **/

    /*
     * 注意：
     * 1.可以组合使用
     * 2.多个泛型约束 用where连接即可
     * **/

}
```

## Lesson52_List知识点

```c#
using System;
using System.Collections.Generic;


namespace Lesson52_List知识点
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("List知识点");

            #region 知识点一 List的本质
            /*
             * List是一个C#为我们封装好的类
             * 它的本质是一个可变类型的泛型数组
             * **/
            #endregion

            #region 知识点二 声明
            //需要引入命名空间 using System.Collections.Generic
            List<int> list = new List<int>();
            #endregion

            #region 知识点三 增删改查
            //增
            list.Add(1);

            list.AddRange(list);

            list.Insert(0, 999);

            //删
            list.Remove(1);

            list.RemoveAt(0);

            //list.Clear();

            //查
            Console.WriteLine(list[0]);

            if (list.Contains(1)){
                Console.WriteLine(list[0]);
            }

            int index = list.IndexOf(1);

            index = list.LastIndexOf(1);


            //改
            Console.WriteLine(list[0]);
            list[0] = 99;
            Console.WriteLine(list[0]);
            #endregion

            #region 知识点四 遍历
            //长度
            Console.WriteLine(list.Count);

            //容量 避免产生垃圾
            Console.WriteLine(list.Capacity);

            for (int i = 0; i < list.Count; i++)
            {
                Console.WriteLine(list[i]);
            }

            foreach (int item in list)
            {
                Console.WriteLine(item);
            }
            #endregion

        }
    }
}
```

## Lesson53_Dictionary

```c#
using System;
using System.Collections.Generic;

namespace Lesson53_Dictionary
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Dictionary");

            #region 知识点一 Dictionary的本质
            //可以将Dictionary理解为 拥有泛型的Hashtable
            //它也是基于键的哈希代码组织起来的 键值对
            //键值对类型从Hashtable的object变为了可以自己制定的泛型
            #endregion

            #region 知识点二 声明
            //需要引入命名空间 using System.Collections.Generic
            Dictionary<int, string> dictionary = new Dictionary<int, string>();
            #endregion

            #region 知识点三 增删改查
            //增 不能出现相同键
            dictionary.Add(1, "123123");
            dictionary.Add(2, "123123");
            dictionary.Add(3, "123123");
            dictionary.Add(4, "123123");

            //删
            //1.只能通过键去删除
            // 删除不存在的键 没有反应不会报错
            dictionary.Remove(1);

            //2.清空
            //dictionary.Clear();

            //查
            //1.通过键查看值 找不到会返回空
            Console.WriteLine(dictionary[1]);
            //2.查看是否存在 根据键检测 根据值检测
            if (dictionary.ContainsKey(1))
            {
                Console.WriteLine(dictionary[1]);
            }

            if (dictionary.ContainsValue("123"))
            {
                Console.WriteLine(dictionary[1]);
            }

            //改
            dictionary[1] = "555";
            #endregion

            #region 知识点四 遍历
            //1.遍历所有键
            foreach (int item in dictionary.Keys)
            {
                Console.WriteLine(item);
                Console.WriteLine(dictionary[item]);
            }
            //2.遍历所有值
            foreach (string item in dictionary.Values)
            {
                Console.WriteLine(item);
            }
            //3.键值对一起遍历
            foreach (KeyValuePair<int,string> item in dictionary)
            {
                Console.WriteLine(item.Key + item.Value);
            }
            #endregion

        }
    }
}
```

## Lesson54_顺序存储和链式存储

```c#
using System;

namespace Lesson54_顺序存储和链式存储
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("顺序存储和链式存储");

            #region 知识点一 数据结构
            /*
             * 数据结构
             * 数据结构是计算机存储 组织数据的方式
             * 数据结构是指相互之间存在一种或多种特定关系的数据元素的集合
             * 比如自定义的一个类 也可以称为一种数据结构 自己定义的数据组合规则
             * **/

            //常用的数据结构
            //数组 栈 队列 链表 树 图 堆 散列表
            #endregion

            #region 知识点二 线性表
            //线性表是一种数据结构 是由n个具有相同特性的数据元素的有限序列
            //比如数组 ArrayList Stack Queue 链表等等
            #endregion

            #region 知识点三 顺序存储
            /*
             * 数组 Stack Queue List ArrayList  -- 顺序存储
             * 只是 数组 Stack Queue的 组织规则不同而已
             * 顺序存储：
             * 用一组地址连续的存储单元依次存储线性表的各个数据元素
             * **/
            #endregion

            #region 知识点四 链式存储
            /*
             * 单向链表 双向链表 循环链表  -- 链式存储
             * 链式存储(链接存储)：
             * 用一组任意的存储单元存储线性表中的各个数据元素
             * **/
            #endregion

        }
    }

    #region 知识点五 自己实现一个最简单的单向链表
    class LinkedNode<T>
    {
        public T value;
        public LinkedNode<T> nextNode;
    }
    #endregion

    #region 知识点六 顺序存储和链式存储的优缺点
    /*
     * 从增删改查角度来看
     * 增：链式存储 计算上 优于顺序存储 (中间插入时链式不用像顺序一样去移动位置)
     * 删：链式存储 计算上 优于顺序存储（中间删除时链式不用像顺序一样去移动位置）
     * 改：顺序存储 使用上 优于链式存储（数组可以直接通过下标得到元素，链式需要遍历）
     * 查：顺序存储 使用上 优于链式存储（数组可以直接通过下标得到元素，链式需要遍历）
     * **/
    #endregion

}
```

## Lesson55_Linkedlist

```c#
using System;
using System.Collections.Generic;

namespace Lesson55_Linkedlist
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Linkedlist");

            #region 知识点一 LinkedList
            //是一个C#为我们封装好的类 它的本质是一个可变类型的泛型双向链表
            #endregion

            #region 知识点二 声明
            //需要引入命名空间
            //using System.Collections.Generic
            LinkedList<int> linkedlist = new LinkedList<int>();
            LinkedList<string> linkedlist1 = new LinkedList<string>();

            //链表对象 需要掌握两个类
            //一个是链表本身 一个是链表节点类 LinkedListNode
            #endregion

            #region 知识点三 增删改查

            //增
            //1.在链表尾部添加元素
            linkedlist.AddLast(10);
            //2.在链表头部添加元素
            linkedlist.AddFirst(20);
            //3.在某一节点之后添加一个节点
            //  要指定节点 先得到一个节点
            LinkedListNode<int> n = linkedlist.Find(20);
            linkedlist.AddAfter(n, 15);
            //4.在某一个节点之前 添加一个节点
            // 要指定节点 先得到一个节点
            linkedlist.AddBefore(n, 11);

            //删
            //1.移除头节点
            linkedlist.RemoveFirst();
            //2.移除尾节点
            linkedlist.RemoveLast();
            //3.移除指定节点
            //无法通过位置直接移除
            linkedlist.Remove(20);
            //4.清空
            //linkedlist.Clear();

            //查
            //1.头节点
            LinkedListNode<int> first = linkedlist.First;
            //2.尾节点
            LinkedListNode<int> last = linkedlist.Last;
            //3.找到指定值的节点
            //无法直接通过下标获取中间元素
            //只有遍历查找指定位置元素
            LinkedListNode<int> node = linkedlist.Find(3);
            Console.WriteLine(node.Value);
            //4.判断是否存在
            if (linkedlist.Contains(1))
            {
                Console.WriteLine("链表中存在...");
            }

            //改
            //要先得到再改 得到节点 再改变其中的值
            linkedlist.First.Value = 10;

            #endregion

            #region 知识点四 遍历

            //1.foreach遍历
            foreach (int item in linkedlist)
            {
                Console.WriteLine(item);
            }

            //2.通过节点遍历
            //从头到尾
            LinkedListNode<int> nowHead = linkedlist.First;
            while(nowHead != null)
            {
                Console.WriteLine(nowHead.Value);
                nowHead = nowHead.Next;
            }

            //从尾到头
            nowHead = linkedlist.Last;
            while (nowHead != null)
            {
                Console.WriteLine(nowHead.Value);
                nowHead = nowHead.Previous;
            }

            #endregion

        }
    }
}
```

## Lesson56_泛型栈和队列

```c#
using System;
using System.Collections.Generic;

namespace Lesson56_泛型栈和队列
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("泛型栈和队列");

            #region 知识点一 回顾数据容器

            //变量

            //复杂数据容器
            /*
             * 枚举 menu
             * 结构体 struct
             * 数组 一维二维交错 [] [,] [][]
             * 类
             * **/

            //数据集合
            /*
             * using System.Collections.Generic
             * 
             * ArrayList object数据列表
             * Stack 栈 先进后出
             * Queue 队列 先进先出
             * Hashtable 哈希表 键值对
             * **/

            //泛型数据集合
            /*
             * using System.Collections.Generic
             * 
             * List 列表 泛型列表
             * Dictionary 字典 泛型哈希表
             * LinkedList 双向链表
             * Stack 泛型栈
             * Queue 泛型队列
             * **/

            #endregion

            #region 知识点二 泛型栈和队列
            //命名空间：using System.Collections.Generic
            //使用上 和之前的Stack和Queue一模一样
            Stack<int> stack = new Stack<int>();
            Queue<int> queue = new Queue<int>();

            #endregion

        }
    }
}
```

## Lesson57_委托

```c#
using System;

namespace Lesson57_委托
{
    #region 知识点一 委托是什么 
    /*
     * 委托是函数的容器
     * 可以理解为表示函数的变量类型
     * 用来存储 传递函数
     * 委托的本质是一个类 用来定义函数的类型(返回值和参数的类型)
     * 不同的函数必须对应和各自格式一致的委托
     * **/
    #endregion

    #region 知识点二 基本语法
    /*
     * 关键字 ： delegate
     * 语法 ： 访问修饰符 delegate 返回值 委托名(参数列表);
     * 
     * 可以声明在namespace和class语句块中
     * 更多的写在namespace中
     * 
     * 简单记忆委托语法 就是 函数声明语法前面加一个delegate关键字
     * **/
    #endregion

    #region 知识点三 定义自定义委托
    /*
     * 访问修饰符默认不写为public 在别的命名空间中也能使用
     * private 其他命名空间中就不能使用
     * 一般使用public
     * 
     * 声明了一个可以用来存储无参无返回值函数的容器
     * 这里只是定义了规则 并没有使用
     * **/
    delegate void MyFun();

    //委托规则的声明 是不能重名(同一语句块中)
    //表示用来装载或者传递 返回值为int 有一个int参数的函数的 委托 容器规则
    delegate int MyFun1(int i);

    //委托是支持泛型的 可以让返回值和参数可变 更方便我们的使用
    delegate T MyFun3<T, K>(T t, K k);
    #endregion

    #region 知识点四 使用定义好的委托
    /*
     * 委托变量是函数的容器
     * 
     * 委托常用在：
     * 1.作为类的成员
     * 2.作为函数的参数
     * **/


    #endregion

    #region 知识点五 委托变量可以存储多个函数（多播委托）

    class Test
    {
        public MyFun fun;
        public MyFun1 fun1;
        public Action action;
        public void TestFun(MyFun fun, MyFun1 fun1)
        {
            //先处理一些别的逻辑 当这些逻辑处理完了 再执行传入的函数 
            fun();
            fun1(1);
            this.fun = fun;
            this.fun1 = fun1;
        }
        #region 增

        public void AddFun(MyFun fun, MyFun1 fun1)
        {
            this.fun += fun;
            this.fun1 += fun1;
        }

        #endregion

        #region 删

        public void ReMoveFun(MyFun fun,MyFun1 fun1)
        {
            //this.fun = this.fun - fun;
            this.fun -= fun;
            this.fun1 -= fun1;
        }

        #endregion

    }




    #endregion



    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("委托");
            //专门用来装载 函数的 容器
            MyFun f = new MyFun(Fun);

            f.Invoke();

            Test t = new Test();

            MyFun f2 = Fun;
            f2();

            MyFun1 f3 = Fun2;
            Console.WriteLine( f3(1) );

            //如何用委托存储多个函数
            MyFun ff1 = null;
            MyFun ff = Fun;
            ff += Fun;
            ff();
            //从容器中移除指定的函数 多移除不会报错 只是不会处理
            ff -= Fun;
            ff();
            //清空容器
            ff = null;
            if(ff != null)
            {
                ff();
            }

            t.AddFun(Fun, Fun2);
            t.fun();
            t.fun1(5);

            #region 知识点六 系统定义好的委托

            //无参无返回值的委托
            Action action = Fun;
            action();

            //可以指定返回值类型的 泛型委托
            Func<string> funcString = Fun3;

            //可以传N个参数的 系统提供了 1到16个参数的委托 直接可以用
            Action<int, string> action1 = Fun4;

            //可以传n个参数 并且有返回值的 系统也提供了 16个委托
            Func<int, int> func2 = Fun2;
            #endregion

        }

        static void Fun()
        {
            Console.WriteLine("123123");
        }

        static int Fun2(int value)
        {
            return value;
        }

        static string Fun3()
        {
            return "";
        }

        static void Fun4 (int i,string str)
        {
            return;
        }


    }

    /*
     * 总结：
     * 简单理解 委托就是装载 传递函数的容器 
     * 可以用委托变量来存储函数或者传递函数的
     * 系统已经提供很多委托给我们用
     * Action： 没有返回值 系统提供了 0-16个委托给我们用
     * Func：有返回值 参数提供了 0-16 个委托给我们用
     * **/
}
```

## Lesson58_事件

```c#
using System;

namespace Lesson58_事件
{
    #region 知识点一 事件是什么
    /*
     * 事件是基于委托的存在
     * 事件是委托的安全包裹
     * 让委托的使用更具有安全性
     * 事件 是一种特殊的变量类型
     * **/
    #endregion

    #region 知识点二 事件的使用
    /*
     * 声明语法：
     * 访问修饰符 event 委托类型 事件名；
     * 事件的使用：
     * 1.事件是作为 成员变量存在于类中
     * 2.委托怎么用 事件就怎么用
     * 事件相对于委托的区别：
     * 1.不能在类外部 赋值
     * 2.不能在类外部 调用
     * 注意：
     * 它只能作为成员存在于类和接口以及结构体中
     * 事件不能作为临时变量在函数中使用
     * **/
    class Test
    {
        //委托成员变量 用于存储 函数的
        public Action myFun;
        //事件成员变量 用于存储 函数的
        public event Action myEvent;

        public Test()
        {
            //事件的使用和委托 一模一样 只是有些 细微的区别
            myFun = TestFun;
            myEvent = TestFun;

            myEvent += TestFun;
            myEvent = myEvent + myFun;
        }
        public void TestFun()
        {

        }
    }

    #endregion

    #region 知识点三 为什么有事件
    /*
     * 1.防止外部随意置空事件
     * 2.防止外部随意调用委托
     * 3.事件相当于对委托进行了一次封装 让其更加安全
     * **/
    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("事件");

            Test t = new Test();

            t.myFun = Fun;
            t.myFun += Fun;
            t.myEvent += Fun;
            //事件不能直接使用赋值运算 但是可以使用复合运算符
            //t.myEvent = Fun;

        }

        static void Fun()
        {

        }

    }
    /*
     * 事件和委托的区别
     * 事件和委托的使用是基本相同的
     * 事件就是特殊的委托
     * 主要区别：
     * 1.事件不能在外部使用赋值符号 只能使用 + - 委托 哪里都能用
     * 2.事件不能在外部执行 委托哪里都能执行
     * 3.事件 不能作为 函数中的临时变量 委托可以
     * **/
}
```

## Lesson59_匿名函数

```c#
using System;

namespace Lesson59_匿名函数
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("匿名函数");
            #region 知识点一 什么是匿名函数
            /*
             * 没有名字的函数
             * 匿名函数的使用主要是配合委托和事件进行使用
             * 脱离委托和事件 是不会使用匿名函数的
             * **/
            #endregion

            #region 知识点二 基本语法

            //delegate (参数列表)
            //{
            //    函数逻辑
            //};
            //什么时候用
            //1.函数中传递委托参数时
            //2.委托或事件赋值时

            #endregion

            #region 知识点三 使用
            //1.无参无返回
            //这样声明匿名函数 只是在声明 函数 还没有调用
            //真正调用它的时候 是这个委托容器什么时候调用 就什么时候调用这个匿名函数
            Action a = delegate ()
            {
                Console.WriteLine("匿名函数");
            };

            a();
            //2.有参
            Action<int,string> b = delegate (int a, string b)
            {
                Console.WriteLine(a);
                Console.WriteLine(b);
            };
            b(100, "123");
            //3.有返回值
            Func<string> c = delegate ()
            {
                return "123";
            };
            Console.WriteLine( c() );
            //4.一般情况会作为函数参数传递 或者 作为函数返回值
            Test t = new Test();
            Action ac = delegate ()
            {
                Console.WriteLine("随参数传入的匿名函数逻辑");
            };
            t.Dosomthing(100, ac);
            //  参数传递
            t.Dosomthing(100,delegate() 
            {
                Console.WriteLine("随参数传入的匿名函数逻辑");
            });
            //  返回值
            Action ac2 = t.GetFun();
            ac2();

            t.GetFun()();//直接调用返回的委托函数
            #endregion

            #region 知识点四 匿名函数的缺点
            //添加到委托或事件容器中后 不记录 无法单独移除

            Action ac3 = delegate ()
            {
                Console.WriteLine("匿名函数一");
            };

            ac3 += delegate ()
            {
                Console.WriteLine("匿名函数二");
            };

            //因为匿名函数没有名字 所以没有办法指定移除某一个匿名函数
            ac3();
            #endregion

        }
    }

    class Test
    {
        public Action action;

        public void Dosomthing(int a ,Action fun)
        {
            Console.WriteLine(a) ;
            fun();
        }

        public Action GetFun()
        {
            return delegate() {
                Console.WriteLine("返回值是一个匿名函数");
            };
        }

        public void TestTTTT()
        {

        }

    }

    //总结：
    //匿名函数 就是没有名字的函数 
    //固定写法
    //delegate(参数列表) {};
    //主要是在 委托传递和存储时 为了方便可以直接使用匿名该函数
    //缺点 没有办法指定移除
}
```

## Lesson60_Lambda表达式

```c#
using System;

namespace Lesson60_Lambda表达式
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Lambda表达式");

            #region 知识点一 什么是Lambad表达式
            /*
             * 可以将Lambda表达式 理解为匿名函数的简写
             * 它除了写法不同外
             * 使用上和匿名函数一模一样
             * 都是和委托或者事件 配合使用的
             * **/
            #endregion

            #region 知识点二 Lambda表达式语法

            //匿名函数
            /*
             * delegate(参数列表)
             * {
             *  
             * };
             * **/

            //Lambda表达式
            /*
             * (参数列表) =>
             * {
             *      //函数体
             * };
             * **/
            #endregion

            #region 知识点三 使用

            //1.无参无返回
            Action a = () =>
            {
                Console.WriteLine("无参无返回的Lambda表达式");
            };
            a();
            //2.有参
            Action<int> a2 = (int value) =>
            {
                Console.WriteLine("有参数的lambda表达式 + {0}",value);
            };
            a2(2);
            //3.甚至参数类型都可以省略 参数类型和委托或事件容器一致
            Action<int> a3 = (value) => { Console.WriteLine("省略参数类型的写法 且是一句话语句 + {0}",value); };
            a3(222);
            //4.有返回值
            Func<string, int> a4 = (value) =>
             {
                 Console.WriteLine("有返回值有参数的lambda表达式 + {0}",value);
                 return 5;
             };
            Console.WriteLine( a4("123") );
            //其他传参使用等和匿名函数一样
            //缺点也是和匿名函数一样的


            #endregion

            Test t = new Test();
            t.Dosomething();
        }
    }

    #region 知识点四 闭包

    /*
     * 内层的函数可以引用包含在它外层的函数的变量
     * 即使外层函数的执行已经终止
     * 注意：
     * 该变量提供的值并非变量创建时的值 而是在父函数范围内的最终值
     * **/

    class Test
    {
        public event Action action;
        public Test()
        {
            int value = 10;

            //这里就形成闭包 
            //因为当构造函数执行完毕时 其中声明的临时变量的生命周期被改变了
            action = () =>
            {
                Console.WriteLine(value);
            };

            for (int i = 0; i < 10; i++)
            {
                int index = i;
                action += () =>
                {
                    Console.WriteLine(index);
                };
            }

        }

        public void Dosomething()
        {
            action();
        }

    }

    #endregion

    //总结
    //匿名函数的特殊写法 就是 lambda表达式
    //固定写法 就是 (参数列表)=>{};
    //参数列表 可以直接省略参数类型
    //主要在 委托传递和存储时 为了方便可以直接使用匿名函数或者lambda表达式
    //缺点 不能直接移除指定的函数
}
```

![image-20221109162258248](https://cdn.jsdelivr.net/gh/PopuDiver/Typora-MapDepot/Typora-MapDepot202211091923018.png)

## Lesson61_List排序

```c#
using System;
using System.Collections.Generic;

namespace Lesson61_List排序
{
    class Item:IComparable<Item>
    {
        public int money;
        public Item(int money)
        {
            this.money = money;
        }

        public int CompareTo(Item other)
        {
            //返回值的含义
            //小于0： 放在传入对象的前面
            //等于0： 保持当前的位置不变
            //大于0： 放在传入对象的后面

            //可以简单理解 传入对象的位置 就是0
            //如果返回为负数 就放在左边 也就是前面
            //如果返回为正数 就放在右边 也就是后面

            if(this.money > other.money)
            {
                return 1;
            }
            else
            {
                return -1;
            }

        }
    }

    class ShopItem
    {
        public int id;
        public ShopItem(int id)
        {
            this.id = id;
        } 
    }
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("List排序");

            #region 知识点一 List自带的排序方法
            List<int> list = new List<int>();
            list.Add(2);
            list.Add(3);
            list.Add(5);
            list.Add(1);
            list.Add(9);
            list.Add(8);
            for (int i = 0; i < list.Count; i++)
            {
                Console.WriteLine(list[i]);
            }

            //list提供了排序方法
            list.Sort();
            Console.WriteLine("*******************************");
            for (int i = 0; i < list.Count; i++)
            {
                Console.Write(list[i] + " ");
            }

            //ArrayList中也有sort排序方法
            #endregion

            #region 知识点二 自定义类的排序
            List<Item> itemList = new List<Item>();
            itemList.Add(new Item(45));
            itemList.Add(new Item(46));
            itemList.Add(new Item(48));
            itemList.Add(new Item(40));
            itemList.Add(new Item(20));
            itemList.Add(new Item(100));

            itemList.Sort();
            Console.WriteLine("\n***************************");
            for (int i = 0; i < itemList.Count; i++)
            {
                Console.WriteLine(itemList[i].money);
            }
            #endregion

            #region 知识点三 通过委托函数进行排序
            List<ShopItem> shopItem = new List<ShopItem>();
            shopItem.Add(new ShopItem(2));
            shopItem.Add(new ShopItem(3));
            shopItem.Add(new ShopItem(5));
            shopItem.Add(new ShopItem(12));
            shopItem.Add(new ShopItem(7));
            shopItem.Add(new ShopItem(20));

            //shopItem.Sort(SortShopItem); // 方法一

            //shopItem.Sort(delegate (ShopItem a,ShopItem b){
            //    return a.id - b.id;
            //}); //方法二 匿名函数

            shopItem.Sort((a, b) =>
            {
                return a.id > b.id ? 1 : -1;
            }); //方法三 lambda表达式 配合 三目运算符写法

            Console.WriteLine("*************************");
            for (int i = 0; i < shopItem.Count; i++)
            {
                Console.WriteLine(shopItem[i].id);
            }
            #endregion

        }
        static int SortShopItem(ShopItem a,ShopItem b)
        {
            //传入的两个对象 为列表中的两个对象
            //进行两两比较 用左边的和右边的条件进行比较
            //返回值规则 和之前一样 0做标准 负数在前 正数在后
            //if(a.id > b.id)
            //{
            //    return 1;
            //}
            //else
            //{
            //    return -1;
            //}
            return a.id - b.id;
        }

    }

    //总结：
    //系统自带的变量(int,float......)一般可以直接sort
    //自定义类sort有两种方式
    //1.继承接口 IComparable
    //2.在sort中传入委托函数
}
```

## Lesson62_协变和逆变

```c#
using System;

namespace Lesson62_协变和逆变
{
    #region 知识点一 什么是协变逆变
    /*
     * 协变：
     * 和谐的变化 自然的变化
     * 因为 里氏替换原则 父类可以装子类
     * 所以 子类变父类
     * 比如 string 变成 object
     * 感受是和谐的
     * **/

    /*
     * 逆变：
     * 逆常规的变化 不正常的变化
     * 因为里氏替换原则 父类可以装子类 但是子类不能装父类
     * 所以 父类变子类
     * 比如 object 变成 string
     * 感受是不和谐的
     * **/

    /*
     * 协变和逆变是用来修饰泛型的
     * 协变：out
     * 逆变：in
     * 用于在泛型中 修饰泛型字母的
     * 只有泛型接口和泛型委托能使用
     * **/

    #endregion

    #region 知识点二 作用
    /*
     * 1.返回值 和 参数
     * 用out修饰的泛型 只能作为返回值
     * 
     * 用in修饰的泛型 只能作为参数
     * 
     * 2.结合里氏替换原则理解
     * **/
    //delegate T TestOut<out T>();
    delegate T TestOut<out T>();
    //delegate void TestIn<in T>(T t);
    delegate void TestIn<in T>(T t);

    class Father
    {

    }

    class Son : Father
    {

    }

    interface Test<out T>
    {
        T TestFun();
    }

    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("协变和逆变");

            #region 知识点二 作用(结合里氏替换原则理解)
            //协变 父类总是能被子类替换
            //看起来 Son变成了Father
            TestOut<Son> os = () => {
                return new Son();
            };

            TestOut<Father> of = os;
            Father f = of(); // 实际上 返回的是 os 里面装的函数 返回的是Son

            //逆变 父类总是能被子类替换
            TestIn<Father> iF = (value) =>
            {

            };

            TestIn<Son> iS = iF;
            iS(new Son()); // 实际上调用的是 iF
            #endregion

        }
    }

    //总结：
    //协变 out 
    //逆变 in
    //用来修饰 泛型替代符 只能修饰接口和委托中的泛型

    //作用两点
    //1.out修饰的泛型类型 只能作为返回值类型 in修饰的泛型类型 只能作为 参数类型
    //2.遵循里氏替换原则的 用out和in修饰的 泛型委托 可以相互装载(有父子关系的泛型)
    //协变就是父类泛型委托装子类泛型委托  逆变就是子类泛型委托装父类泛型委托
}
```

## Lesson63_多线程

```c#
using System;
using System.Threading;

namespace Lesson63_多线程
{
    class Program
    {
        static bool isRuning = true;
        static object obj = new object();
        static void Main(string[] args)
        {
            Console.WriteLine("多线程");

            #region 知识点一 了解线程前先了解进程
            /*
             * 进程(Process) 是计算机中的程序关于某数据集合上的一次运行活动
             * 是系统进行资源分配和调度的基本单位 是操作系统结构的基础
             * 打开一个应用程序其实就是在操作系统上开启了一个进程
             * 进程之间可以相互独立运行 互不打扰
             * 进程之间也可以相互访问 操作
             * **/
            #endregion

            #region 知识点二 什么是线程
            /*
             * 操作系统能够进行运算调度的最小单位
             * 它被包含在进程中 是进程中的实际运作单位
             * 一条线程指的是进程中一个单一顺序的控制流 一个进程中可以并发多个线程
             * 我们目前写的程序都在主线程中
             * **/

            //简单理解线程：
            //就是代码从上到下运行的一条管道
            #endregion

            #region 知识点三 什么是多线程
            //我们可以通过代码 开启新的线程
            //可以同时运行代码的多条管道 就叫多线程
            #endregion

            #region 知识点四 语法相关
            /*
             * 线程类 Thread
             * 需要引用命名空间 using System.Threading;
             * 1. 声明一个新的线程
             *      注意 线程执行的代码 需要封装到一个函数中
             * **/
            //新线程将要执行的代码逻辑 被封装到了一个函数语句块中
            Thread t = new Thread(NewThreadLogic);


            //2.启动线程
            t.Start();

            //3.设置为后台线程
            /*
             * 当前台线程都结束了的时候 整个程序也就结束了 即使还有后台线程正在运行
             * 后台线程不会防止应用程序的进程被终止掉
             * 如果不设置为后台线程 可能导致进程无法正常关闭
             * **/
            t.IsBackground = true;

            //4.关闭释放一个线程
            /*
             * 如果开启的线程中不是死循环 是能够结束的逻辑 那么 不用刻意的去关闭它
             * 如果是死循环 想要终止这个线程 有两种方式
             * 4-1.死循环中bool标识
             * **/
            //isRuning = false;

            //Console.ReadKey();

            //4-2.通过线程提供的方法(注意在.Net core版本中无法中止 会报错)
            //中止线程函数
            //try
            //{
            //    t.Abort();
            //    t = null;
            //}
            //catch
            //{

            //}


            //5.线程休眠
            //让线程休眠多少毫秒 1s = 1000ms
            //在哪个线程里执行 就休眠哪个
            //Thread.Sleep(1000);
            #endregion

            #region 知识点五 线程之间共享数据
            /*
             * 多个线程使用的内存是共享的 都属于该应用程序(进程)
             * 所以要注意 当多线程 同时操作同一片内存区域时可能会出问题
             * 可以通过加锁的形式避免问题
             * **/

            //lock关键字
            //当我们在多个线程当中想要访问同样的东西 进行逻辑处理时
            //为了避免不必要的逻辑顺序执行的差错
            //lock(引用类型对象)

            while (true)
            {
                lock (obj)
                {
                    Console.SetCursorPosition(0, 0);
                    Console.ForegroundColor = ConsoleColor.Red;
                    Console.WriteLine("*");
                }
                
            }

            #endregion

            #region 知识点六 多线程对于我们的意义
            //可以用多线程专门处理一些复杂耗时的逻辑
            //比如 寻路 网络通信等
            #endregion
        }
        static void NewThreadLogic()
        {
            //新开线程 执行的代码逻辑 在该函数语句块中
            while (isRuning)
            {
                //Console.WriteLine("这是一个新开线程代码逻辑");
                //Thread.Sleep(1000);

                lock (obj)
                {
                    Console.SetCursorPosition(10, 5);
                    Console.ForegroundColor = ConsoleColor.Yellow;
                    Console.WriteLine("〇");
                }

            }
        }
            
    }

    //总结:
    //多线程是多个可以同时执行代码逻辑的 管道 
    //可以通过代码开启多线程 用多线程处理一些复杂的可能影响主线程流畅度的逻辑
    //关键字 Thread 命名空间 using System.Threading;
}
```

## Lesson64_预处理器指令

```c#
#define Unity5
#define Unity3
using System;

namespace Lesson64_预处理器指令
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("预处理器指令");

            #region 知识点一 什么是编译器
            //编译器是一种翻译程序
            //它用于将源语言程序翻译为目标语言程序

            //源语言程序:某种程序设计语言写成的 比如C#,C,C++,JAVA等语言写的程序
            //目标语言程序 : 二进制数表示的伪机器代码写的程序
            #endregion

            #region 知识点二 什么是预处理器指令
            //预处理指令 指导编译器 在实际编译开始之前对信息进行预处理
            //预处理指令 都是以#开始
            //预处理指令不是语句 所以它们不以分号结束
            //常用的 折叠代码块 就是预处理指令
            #endregion

            #region 知识点三 常见的预处理器指令
            /*
             * 1. #define 定义一个符号 类似一个没有值的变量
             * #undef 取消define定义的符号 让其失效
             * 两者都是写在脚本文件最前面 
             * 一般配合 if指令使用 或配合特性
             * **/

            /*
             * 2.#if
             * #elif
             * #else
             * #endif
             * 和if语句规则一样 一般配合#define定义的符号使用
             * 用于告诉编译器进行编译代码的流程控制
             * **/

            //如果发现有Unity5这个符号 那么其中包含的代码 就会被编译器编译
#if Unity5
            Console.WriteLine("Unity版本为5");
            //#warning 这个版本不合法
            //#error 这个版本报错
#elif Unity4
            Console.WriteLine("Unity版本为4");
#else
            Console.WriteLine("Unity版本为**");
#endif

            /*
             * 3.
             * #warning
             * #error
             * 告诉编译器
             * 是报警告还是错误
             * 一般配合if使用
             * **/

            #endregion
        }
    }
    /*
     * 总结：
     * 预处理器指令
     * 可以让代码还没有编译之前就可以进行一些预处理判断
     * 在Unity中会用来进行一些平台或者版本的判断
     * 决定不同的版本或者不同的平台使用不同的代码逻辑
     * **/
}
```

## Lesson65_反射

```c#
using System;
using System.Reflection;

namespace Lesson65_反射
{
    #region 知识点回顾
    //编译器是一种翻译程序
    //它用于将源语言程序翻译为目标语言程序

    //源语言程序：某种程序设计语言写成的 比如C#，C,C++,JAVA等语言写的程序
    //目标语言程序：二进制数表示的伪机器代码写的程序
    #endregion

    #region 知识点一 什么是程序集
    //程序集是经由编译器编译得到的 供进一步编译执行的那个中间产物
    //在Windows系统中 它一般表现为后缀为.dll(库文件) 或者是 .exe(可执行文件)的格式

    //程序集就是我们写的一个代码集合 我们现在写的所有代码
    //最终都会被编译器翻译为一个程序集供别人使用
    //比如一个代码库文件(dll)或者一个可执行文件(exe)
    #endregion

    #region 知识点二 元数据
    //元数据就是用来描述数据的数据
    //这个概念不仅仅用于程序上 在别的领域也有元数据

    //程序中的类 类中的函数 变量等等信息就是程序的元数据
    //有关程序以及类型的数据被称为元数据 它们保存在程序集中
    #endregion

    #region 知识点三 反射的概念
    /*
     * 程序正在运行时 可以查看其他程序集或者自身的元数据
     * 一个运行的程序查看本身或者其他程序的元数据的行为就叫做反射
     * 
     * 在程序运行时 通过反射可以得到其他程序集或者自己程序集代码的各种信息
     * 类 函数 变量 对象等等 实例化它们 执行它们 操作它们
     * **/
    #endregion

    #region 知识点四 反射的作用
    /*
     * 因为反射可以在程序编译后获得信息 所以它提高了程序的拓展性和灵活性
     * 1.程序运行时得到所有元数据 包括元数据的特性
     * 2.程序运行时 实例化对象 操作对象 
     * 3.程序运行时创建新对象 用这些对象执行任务
     * **/
    #endregion

    class Test
    {
        private int i = 1;
        public int j = 0;
        public string str = "123";
        public Test()
        {

        }

        public Test(int i)
        {
            this.i = i;
        }

        public Test(int i,string str):this(i)
        {
            this.str = str;
        }
        public void Speak()
        {
            Console.WriteLine("Speak");
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("反射");
           
            #region 知识点五 语法相关

            #region Type
            /*
             * Type（类的信息类）
             * 它是反射功能的基础
             * 它是访问元数据的主要方式
             * 使用Type的成员获取有关类型声明的信息
             * 有关类型的成员(如构造函数 成员 字段 属性 和类的事件)
             * **/
            #region 获取Type
            //1.万物之父object中的GetType()可以获取对象的Type
            int a = 42;
            Type type = a.GetType();
            Console.WriteLine(type);
            //2.通过typeof关键字 传入类名 也可以得到对象的Type
            Type type2 = typeof(int);
            Console.WriteLine(type2);
            //3.通过类的名字 也可以获取类型
            //注意 类名必须包含命名空间 不然找不到
            Type type3 = Type.GetType("System.Int32");
            Console.WriteLine(type3);


            #endregion

            #region 得到类的程序集信息
            //可以通过Type可以得到类型所在程序集信息
            Console.WriteLine(type.Assembly);
            #endregion

            #region 获取类中的所有公共成员
            //首先得到Type
            Type t = typeof(Test);
            //然后得到所有公共成员
            //需要引用命名空间 using System.Reflection
            MemberInfo[] infos = t.GetMembers();
            for (int i = 0; i < infos.Length; i++)
            {
                Console.WriteLine(infos[i]);
            }
            #endregion

            #region 获取类的公共构造函数并调用
            //1.获取所有构造函数
            ConstructorInfo[] ctor = t.GetConstructors();
            for (int i = 0; i < ctor.Length; i++)
            {
                Console.WriteLine(ctor[i]);
            }
            //2.获取其中一个构造函数 并执行
            //得构造函数传入Type数组 数组中内容按顺序是参数类型
            //执行构造函数传入 object数组 表示按顺序传入的参数
            // 2-1 得到无参构造
            ConstructorInfo info = t.GetConstructor(new Type[0]);
            //执行无参构造 无参构造 没有参数 传null
            Test obj = info.Invoke(null) as Test;
            Console.WriteLine(obj.j);
            // 2-2 得到有参构造
            ConstructorInfo info2 = t.GetConstructor(new Type[] { typeof(int) });
            obj = info2.Invoke(new object[] { 2 }) as Test;
            Console.WriteLine(obj.str);

            ConstructorInfo info3 = t.GetConstructor(new Type[] { typeof(int), typeof(string) });
            obj = info3.Invoke(new object[] { 2, "123" }) as Test;
            Console.WriteLine(obj.j + " " + obj.str);
            #endregion

            #region 获取类的公共成员变量
            //1.得到所有成员变量
            FieldInfo[] fieldInfos = t.GetFields();
            for (int i = 0; i < fieldInfos.Length; i++)
            {
                Console.WriteLine(fieldInfos[i]);
            }
            //2.得到指定名称的公共成员变量
            FieldInfo infoJI = t.GetField("j");
            Console.WriteLine(infoJ);

            //3.通过反射获取和设置对象的值
            Test test = new Test();
            test.j = 99;
            test.str = "123456";

            //  3-1通过反射 获取对象的某个变量的值
            Console.WriteLine(infoJ.GetValue(test));
            //  3-2通过反射 设置指定对象的某个变量的值
            infoJ.SetValue(test, 100);
            Console.WriteLine(infoJ.GetValue(test));
            #endregion

            #region 获取类的公共成员方法
            //通过Type类中的 GetMethod方法 得到类中的方法
            //MethodInfo 是方法的反射信息
            Type strType = typeof(string);

            //1.如果存在方法重载 用Type数组表示参数类型
            MethodInfo[] methods = strType.GetMethods();
            for (int i = 0; i < methods.Length; i++)
            {
                Console.WriteLine(methods[i]);
            }

            MethodInfo subStr = strType.GetMethod("Substring", new Type[] { typeof(int), typeof(int) });

            //2.调用该方法
            //注意：如果是静态方法 Invoke中的第一个参数传null即可
            string str = "Hello,World!";
            //第一个参数 相当于 是哪个对象要执行这个成员方法
            object result = subStr.Invoke(str, new object[] { 7, 5 });
            Console.WriteLine(result);
            #endregion

            #region 其它
            //Type
            //得枚举
            //GetEnumName
            //GetEnumNames

            //得事件
            //GetEvent
            //GetEvents

            //得接口
            //GetInterface
            //GetInterfaces

            //得属性
            //GetProperty
            //GetPropertys
            //等等
            #endregion

            #endregion

            #region Assembly
            /*
             * 程序集类
             * 主要用来加载其它程序集 加载后
             * 才能用Type来使用其它程序集中的信息
             * 如果想要使用不是自己程序集中的内容 需要先加载程序集
             * 比如 dll文件(库文件)
             * 简单的把库文件看成一种代码仓库 它提供给使用者一些可以直接拿来用的变量 函数或类
             * **/

            //三种加载程序集的函数
            //一般用来加载在同一文件下的其它程序集
            //Assembly asembly2 = Assembly.Load("程序集名称");

            //一般用来加载不在同一文件下的其它程序集
            //Assembly asembly = Assembly.LoadFrom("包含程序集清单的文件的名称或路径");
            //Assembly asembly3 = Assembly.LoadFile("要加载的文件的完全限定路径");

            //1.先加载一个指定程序集
            Assembly assembly = Assembly.LoadFrom(@"D:\C#Train\Lesson65_反射\bin\Debug\netcoreapp3.1\Lesson65_反射.dll");
            Type[] types = assembly.GetTypes();
            for (int i = 0; i < types.Length; i++)
            {
                Console.WriteLine(types[i]);
            }

            //2.再加载程序集中的一个类对象 之后才能使用反射
            Type test2 = assembly.GetType("Lesson65_反射.Test");
            MemberInfo[] members = test2.GetMembers();
            for (int i = 0; i < members.Length; i++)
            {
                Console.WriteLine(members[i]);
            }
            //通过反射 实例化一个 test对象
            //首先得到枚举Type 来得到可以传入的参数
            //直接实例化对象
            //得到对象中的方法 通过反射
            

            //3.类库工程创建

            #endregion

            #region Activator
            /*
             * 用于快速实例化对象的类
             * 用于将Type对象快捷实例化为对象
             * 先得到Type
             * 然后 快速实例化一个对象
             * **/
            Type testType = typeof(Test);
            //1.无参构造
            Test testObj = Activator.CreateInstance(testType) as Test;
            Console.WriteLine(testObj.str);
            //2.有参构造 参数要和构造函数对应
            testObj = Activator.CreateInstance(testType, 99,"11123331") as Test;
            Console.WriteLine(testObj.j);
            #endregion

            #endregion

        }
    }

    //总结：
    //反射
    //在程序运行时 通过反射可以得到其它程序集或者自己的程序集代码的各种信息
    //类 函数 变量 对象 等等 实例化它们 执行它们 操作他们

    //关键类
    //Type
    //Assembly
    //Activator

    //对于我们的意义
    //在初中级阶段 基本不会使用反射
    //先作为了解 了解反射可以做什么

    //学习反射 是为了以后unity引擎的基本工作原理
    //unity引起的基本工作机制 就是建立在反射的基础上
}
```

## Lesson66_特性

```c#
#define Fun
using System;
using System.Runtime.CompilerServices;
using System.Diagnostics;
using System.Runtime.InteropServices;

namespace Lesson66_特性
{
    #region 知识点一 特性是什么
    //特性是一种允许我们向程序的程序集添加元数据的语言结构
    //它是用于保存程序结构信息的某种特殊类型的类

    //特性提供功能强大的方法以将声明信息与C#代码(类型 方法 属性等)相关联
    //特性与程序实体关联后 即可在运行时使用反射查询特性信息

    //特性的目的是告诉编译器把程序结构的某组元数据嵌入程序集中
    //它可以放置在几乎所有的声明中 (类 变量 函数 等等声明)

    //特性本质是个类
    //我们可以利用特性类为元数据添加额外信息
    //比如一个类 成员变量 成员方法等等为它们添加更多的额外信息
    //之后可以通过反射来获取这些额外信息
    #endregion

    #region 知识点二 自定义特性
    //继承特性基类 Attribute
    [AttributeUsage(AttributeTargets.Class | AttributeTargets.Field,AllowMultiple = true,Inherited = false)]
    class MyCustomAttribute:Attribute
    {
        //特性中的成员 一般根据需求来写
        public string info;
        public MyCustomAttribute(string info)
        {
            this.info = info;
        }
        public void TestFun()
        {
            Console.WriteLine("特性的方法");
        }
    }
    #endregion

    #region 知识点三 特性的使用
    /*
     * 基本语法：
     * [特性名(参数列表)]
     * 本质上 就是再调用特性类的构造函数
     * 写在哪里？
     * 类 函数 变量 上一行 表示他们具有该特性信息
     * **/

    [MyCustom("这个是自定义的测试类")]
    class MyClass
    {
        [MyCustom("用于测试的成员变量")]
        public int a;

        //[MyCustom("用于测试的成员方法")]
        //public void TestFun([MyCustom("用于测试的成员函数的参数")]int a)
        //{
        //    //Console.WriteLine("特性的方法");
        //}

        public void TestFun(int a)
        {
            //Console.WriteLine("特性的方法");
        }
    }
    #endregion

    #region 知识点四 限制自定义特性的使用范围
    //通过为特性类 加特性 限制其使用范围
    [AttributeUsage(AttributeTargets.Class | AttributeTargets.Struct,AllowMultiple = true,Inherited = true) ]
    //参数一 ： AttributeTargets -- 特性能用在哪些地方
    //参数二 ： AllowMultiple -- 是否允许多个特性实例用在同一目标上
    //参数三 ： Inherited -- 特性是否都被派生类和重写成员继承
    public class MyCustom2Attribute : Attribute
    {

    }
    #endregion

    #region 知识点五 系统自带特性 -- 过时特性
    /*
     * 过时特性
     * Obsolete
     * 用于提示用户 使用的方法等成员已经过时 建议使用新方法
     * 一般加在函数前的特性
     * **/

    class TestClass
    {
        //参数一 调用过时方法时 提示的内容
        //参数二 true-使用该方法时会报错 false-使用该方法时会直接警告
        [Obsolete("OldSpeak方法已经过时了 请使用Speak方法",false)]
        public void OldSpeak()
        {
            Console.WriteLine("OldSpeak");
        }

        public void Speak()
        {

        }

        public void SpeakCaller(string str,[CallerFilePath]string fileName = "",
            [CallerLineNumber]int line = 0,[CallerMemberName]string target = "")
        {
            Console.WriteLine(str);
            Console.WriteLine(fileName);
            Console.WriteLine(line);
            Console.WriteLine(target);
        }

    }

    #endregion

    #region 知识点六 系统自带特性 -- 调用者信息特性
    /*
     * 哪个文件调用
     * CallerFilePath特性
     * 哪一行调用？
     * CallerLineNumber特性
     * 哪个函数调用？
     * CallerMemberName特性
     * **/

    //需要引用命名空间 using System.Runtime.CompileerServices;
    //一般作为函数参数的特性
    #endregion

    #region 知识点七 系统自带特性 -- 条件编译特性
    /*
     * 条件编译特性
     * Conditional
     * 它会和预处理指令 #define配合使用
     * 
     * 需要引用命名空间 using System.Diagnostics;
     * 主要可以用在一些调试代码上
     * 有时想执行有时不想执行的代码
     * **/
    #endregion

    #region 知识点八 系统自带特性 -- 外部Dll包函数特性
    //DllImport

    /*
     * 用来标记非.Net(C#)的函数 表明该函数在一个外部的Dll中定义 
     * 一般用来调用C或者C++的Dll包写好的方法
     * 需要引用命名空间 using System.Runtime.InteropServices
     * **/
    #endregion
    class Program
    {
        [DllImport("Test.dll")]
        public static extern int Add(int a, int b);

        [Conditional("Fun")]
        static void Fun()
        {
            Console.WriteLine("Fun执行");
        }

        static void Main(string[] args)
        {
            Console.WriteLine("特性");

            #region 特性的使用
            MyClass mc = new MyClass();
            Type t = mc.GetType();
            //t = typeof(MyClass);
            //t = Type.GetType("Lesson66_特性.MyClass");

            //判断是否使用了某个特性
            //参数一 特性的类型 参数二 代表是否搜索继承链(属性和事件忽略此参数)
            if (t.IsDefined(typeof(MyCustomAttribute), false))
            {
                Console.WriteLine("该类型应用了MyCuston特性");
            }

            //获取Type元数据中的所有特性
            object[] array = t.GetCustomAttributes(true);
            for (int i = 0; i < array.Length; i++)
            {
                if(array[i] is MyCustomAttribute)
                {
                    Console.WriteLine((array[i] as MyCustomAttribute).info);
                    (array[i] as MyCustomAttribute).TestFun();
                }
            }

            TestClass tc = new TestClass();
            tc.OldSpeak();
            tc.Speak();

            tc.SpeakCaller("123231546");

            Fun();
            #endregion

        }
    }

    /*
     * 总结：
     * 特性是用于 为元数据再添加更多的额外信息(变量 方法 等等)
     * 我们可以通过反射 获取这些额外的数据 来进行一些特殊的处理
     * 自定义特性 -- 继承 Attribute类
     * **/

    //系统自带特性 ： 过时特性 

    //为什么要学习特性
    //Unity引擎中很多地方都用到了特性来进行一些特殊处理
}
```

## Lesson67_迭代器

```c#
using System;
using System.Collections;

namespace Lesson67_迭代器
{
    #region 知识点一 什么是迭代器
    /*
     * 迭代器(iterator)有时又称光标(cursor)
     * 是程序设计的软件设计模式
     * 迭代器模式提供一个方法顺序访问一个聚合对象中的各个元素
     * 而又不暴露其内部的标识
     * **/

    /*
     * 在表现效果上看
     * 是可以在容器对象 (例如链表或数组)上遍历访问的接口 
     * 设计人员无需关心容器对象的内存分配的实现细节
     * 可以用foreach遍历的类 都是实现了迭代器的
     * **/
    #endregion

    #region 知识点二 标准迭代器的实现方法
    /*
     * 关键接口：IEnumerator，IEnumerable
     * 命名空间：using System.Collections;
     * 可以通过同时继承IEnumerable和IEnumerator实现其中的方法
     * **/

    class CustomList: IEnumerable,IEnumerator
    {
        private int[] list;
        //从-1开始的光标 用于表示数据得到了哪个位置
        private int position = -1;
        public CustomList()
        {
            Console.WriteLine("迭代器。。。");
            list = new int[] { 1, 2, 3, 4, 5, 6, 7, 8, 9 };
        }

        #region IEnumerable
        public IEnumerator GetEnumerator()
        {
            Reset();
            return this;
        }

        #endregion

        public object Current
        {
            get
            {
                return list[position];
            }
        }

        public bool MoveNext()
        {
            //移动光标
            ++position;
            //是否溢出 溢出就不合法
            return position < list.Length;
            //throw new NotImplementedException();
        }

        //Reset是重置光标位置 一般是写在获取IEnumerator对象这个函数中
        //用于第一次重置光标位置
        public void Reset()
        {
            position = -1;
        }

    }

    #endregion

    #region 知识点三 用yield return 语法糖实现迭代器
    /*
     * yield return是C#提供给我们的语法糖
     * 所谓语法糖 也就是糖衣语法 
     * 主要作用就是将复杂逻辑简单化 可以增加程序的可读性
     * 从而减少程序代码出错的机会 
     * **/

    /*
     * 关键接口 IEnumerable
     * 命名空间 using System.Collections;
     * 让想要通过foreach遍历的自定义类实现接口中的方法GetEnumerator即可
     * **/

    class CustomList2 : IEnumerable
    {
        private int[] list;
        public CustomList2()
        {
            list = new int[] { 1, 2, 3, 4, 5, 6, 7, 8, 9 };
        }
        public IEnumerator GetEnumerator()
        {
            for (int i = 0; i < list.Length; i++)
            {
                //yield关键字 配合迭代器使用
                //可以理解为暂时返回 保留当前状态
                //一会还会再回来
                //C#的语法糖
                yield return list[i];
            }

            //yield return list[0];
            //yield return list[1];
            //yield return list[2];
            //yield return list[3];
            //yield return list[4];
            //yield return list[5];
            //yield return list[6];
            //yield return list[7];
            //yield return list[8];
        }
    }

    #endregion

    #region 知识点四 用 yield return 语法糖为泛型类 实现迭代器
    class CustomList<T> : IEnumerable
    {
        private T[] array;
        public CustomList(params T[] array)
        {
            this.array = array;
        }
        public IEnumerator GetEnumerator()
        {
            for (int i = 0; i < array.Length; i++)
            {
                yield return array[i];
            }
        }
    }
    #endregion

    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("迭代器");

            CustomList list = new CustomList();

            //foreach本质
            //1.先获取in后面这个对象的 IEnumerator
            // 会调用对象其中的GetEnumerator方法来获取
            //2.执行得到这个IEnumerator对象中的 MoveNext方法
            //3.只要MoveNext方法的返回值是true 就会去得到Current
            // 然后赋值给 item 
            //foreach (int item in list)
            //{
            //    Console.WriteLine(item);
            //}

            //CustomList2 list2 = new CustomList2();
            //foreach (int item in list2)
            //{
            //    Console.WriteLine(item);
            //}

            CustomList<string> list2 = new CustomList<string>("123","321","456","654");
            foreach (string item in list2)
            {
                Console.WriteLine(item);
            }
        }
    }
}

//总结：
//迭代器就是可以让我们在外部直接通过foreach遍历对象中元素而不需要了解其结构
//主要的两种方式
//1.传统方式 继承两个接口 实现里面的方法
//2.用语法糖 yield return 去返回内容 只需要继承一个接口即可
```

## Lesson68_特殊语法

```c#
using System;
using System.Collections.Generic;

namespace Lesson68_特殊语法
{
    class Person
    {
        private int money;
        public bool sex;

        public string Name
        {
            get => "Hello World!";
            set => sex = true;
        }

        public int Age
        {
            get; 
            set ;
        }

        public Person(int money)
        {
            this.money = money;
        }
        public int Add(int x, int y) => x + y;

        public void Speak(string str) => Console.WriteLine(str);
    }
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("特殊语法");

            #region 知识点一 var隐式类型
            /*
             * var是一种特殊的变量类型
             * 它可以用来表示任意类型的变量
             * 注意：
             * 1.var不能作为类的成员 只能用于临时变量声明时
             *      也就是 一般写在函数语句块中
             * 2.var必须初始化
             * **/

            var i = 5;
            var s = "123";
            var array = new int[] { 1, 23, 2, 5, };
            var list = new List<int>();

            #endregion

            #region 知识点二 设置对象初始值
            //声明对象时
            //可以通过直接写大括号的形式初始化公共变量和属性

            Person p = new Person (100){ sex = true,Age = 18,Name = "HW"};
            Person p2 = new Person(200) { Age = 18 };
            #endregion

            #region 知识点三 设置集合初始值
            //声明集合对象时
            //也可以通过大括号 直接初始化内部属性

            int[] array2 = new int[] { 1, 2, 3, 4, 5 };

            List<int> listInt = new List<int>() { 1, 2, 3, 4, 5, 6 };

            List<Person> listPerson = new List<Person>() {
                new Person(200),
                new Person(100){Age = 12}
            };

            Dictionary<int, string> dic = new Dictionary<int, string>()
            {
                {1,"123" },
                {2,"222" }
            };
            #endregion

            #region 知识点四 匿名类型
            //var 变量可以声明为自定义的匿名类型
            var v = new { age = 10, money = 11, name = "123" };
            Console.WriteLine(v.age);
            #endregion

            #region 知识点五 可空类型
            //1.值类型是不能赋值为 空的

            //2.声明时 在值类型后面加？可以赋值为空
            int? c = null;
            //3.判断是否为空
            if (c.HasValue)
            {
                Console.WriteLine(c);
                Console.WriteLine(c.Value);
            }
            //4.安全获取可空类型值
            int? value = null;
            //4-1.如果为空 默认返回值类型的默认值
            Console.WriteLine(value.GetValueOrDefault());
            //4-2.也可以指定一个默认值
            Console.WriteLine(value.GetValueOrDefault(100));

            object o = null;
            if(o != null)
            {
                o.ToString();
            }
            //相当于一种语法糖 能够帮助我们自动去判断o是否为空
            //如果是null就不会执行tostring也不会报错
            o?.ToString();

            int[] arrayInt = null;

            Console.WriteLine(arrayInt?[0]);

            Action action = null;
            if (action != null)
                action();

            action?.Invoke();

            #endregion

            #region 知识点六 空合并操作符
            /*
             * 空合并操作符 ？？
             * 左边值 ？？ 右边值
             * 如果左边值为null 就返回右边值 否则返回左边值
             * 只要是可以为null的类型都能用
             * **/

            int? intV = null;
            int intI = intV == null ? 100 : intV.Value;
            intI = intV ?? 100;
            Console.WriteLine(intI);

            string str = null;
            str = str ?? "Hello World!";
            Console.WriteLine(str);

            #endregion

            #region 知识点七 内插字符串
            //关键符号 ： $
            //用$来构造字符串 让字符串可以拼接变量

            string name = "123456";
            int age = 18;
            Console.WriteLine($"Hello World!,{name},{age}");

            #endregion

            #region 知识点八 单句逻辑简略写法
            //当循环或者if语句中只有 一句代码的时候 可以省略大括号
            if(true)
                Console.WriteLine("单句逻辑");

            int j = 0;
            for (; j < 10; j++) ;
                Console.WriteLine(j);
            #endregion

        }
    }
}
```

## Lesson69_值类型和引用类型详解

### 1.如何判断值类型和引用类型

在内部判断来说：

如果进入一个数据类型内部去看 如果是class就是引用类型 如果是struct就是值类型

### 2.语句块

​               命名空间
​                  			⬇
​              	类 接口 结构体
​                   			↓
函数 属性 索引器 运算符重载等(类 接口 结构体)
​                 			  ↓
​             	 条件分支 循环

上层语句块：类 结构体
		中层语句块：函数
		底层的语句块 ： 条件分支 循环等

我们的逻辑代码写在哪里
		函数 条件分支 循环-中底层语句块中

我们的变量可以声明在哪里？
		上中底层都能声明变量
		上层语句块中：成员变量
		中底层语句块中：临时变量

### 3.变量的生命周期

编程时大部分都是临时变量，在中底层声明的临时变量(函数，条件分支，循环语句块等)

语句块执行结束，没有被记录的对象被回收或变成垃圾

值类型：被系统自动回收

引用类型：栈上用于存地址的房间被系统自动回收 堆中具体内容变成垃圾，待下次GC自动回收

**想要不被回收或者不变垃圾，必须将其记录下来，在更高层级记录或者使用静态全局变量记录

### 4.结构体中的值和引用

结构体本身是值类型

前提：该结构体没有作为其他类的成员

在结构体中的值：栈中存储值具体的内容

在结构体中的引用：堆中存储引用具体的内容

**引用类型始终存储在堆中，真正通过结构体使用具体引用类型时只是根据地址寻找

### 5.类中的值和引用

类本身是引用类型

在类中的值，堆中存储具体的值

在类中的引用，堆中存储具体的值

***值类型跟着语句块走，引用类型一直都是存储在堆中

### 6.数组中的存储规则

数组本身是引用类型

值类型数组：堆中房间存具体内容

引用类型数组：堆中房间存储具体内容的地址

### 7.结构体继承接口

利用里氏替换原则，用接口容器装载结构体存在装箱拆箱



###    
