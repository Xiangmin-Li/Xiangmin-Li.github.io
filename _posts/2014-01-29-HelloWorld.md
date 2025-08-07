---
layout:     post
title:      "Hello World"
subtitle:   " \"Hello World, Hello Blog\""
date:       2025-08-7 20:00:00
author:     "Xiangmin Li"
header-img: "img/post-bg-2015.jpg"
catalog: true
#tags:
---


C#

# 代码基本结构

```c# title="基本结构"
// 引入System命名空间
using System;

// 定义程序的主命名空间，用于组织相关代码
namespace BasicStructureDemo 
{
    // 主程序类，包含程序入口点和功能方法
    class Program 
    {
        // 程序入口方法（必须为static void），程序启动时自动执行
        static void Main() 
        {
            // 基础输出演示
            Console.WriteLine("Hello C# World!");

            // 变量声明与条件判断
            int number = 10;
            
            if (number > 5) 
            {
                // 使用字符串插值语法（$符号）输出变量值
                Console.WriteLine($"数字 {number} 大于5");
            }

            // 调用自定义方法打印当前时间
            PrintCurrentTime();
        }

        // 自定义静态方法（可在不创建对象的情况下调用）
        static void PrintCurrentTime() 
        {
            // 获取系统当前时间并格式化输出
            Console.WriteLine($"当前时间：{DateTime.Now}");
        }
    }
}

```


# 开发文件结构

```c# 
[项目根目录]
│
├── MySolution.sln                // 解决方案文件，管理多个项目的关联关系和构建配置
│
├── MyProject/                     // 主项目文件夹
│   │
│   ├── MyProject.csproj           // 项目配置文件 (XML格式)
│   │   ├── <PropertyGroup>        // 定义编译参数
│   │   │   ├── <TargetFramework>net8.0</TargetFramework>
│   │   │   ├── <OutputType>Exe</OutputType>
│   │   │   └── <Nullable>enable</Nullable>
│   │   │
│   │   ├── <ItemGroup>            // 管理依赖项
│   │   │   ├── <PackageReference Include="Newtonsoft.Json" Version="13.0.1" />
│   │   │   └── <ProjectReference Include="..\MyLib\MyLib.csproj" />
│   │
│   ├── Program.cs                 // 主程序入口类
│   │   └── static void Main() { ... } // 程序启动入口
│   │
│   ├── Services/                  // 业务逻辑层
│   │   └── DataService.cs         // 示例服务类
│   │
│   ├── Models/                    // 数据模型
│   │   └── User.cs                // 示例模型类
│   │
│   ├── Properties/
│   │   └── AssemblyInfo.cs        // 程序集元数据配置
│   │       └── [assembly: AssemblyVersion("1.0.0.0")]
│   │
│   ├── bin/                       // 编译输出目录
│   │   ├── Debug/                 // 调试模式
│   │   │   ├── MyProject.exe      // 生成的可执行文件
│   │   │   └── MyProject.pdb      // 调试符号文件
│   │
│   ├── obj/                       // 中间编译文件
│   │   └── Debug/
│   │       ├── net8.0/
│   │       │   └── MyProject.dll  // 中间程序集
│   │
│   └── appsettings.json          // 应用程序配置
│
├── MyLib/                         // 类库项目
│   └── MyLib.csproj               // 类库项目配置
│
└── .gitignore                    // Git版本控制忽略规则
```


# 类型

```c# 
class VariableTypesDemo
{
    enum Status { Active, Inactive }  // 枚举类型

    struct Point
    {
        public int X, Y;
    }  // 结构体类型

    public void fuck()
    {
        // 值类型
        int age = 25;               // 整型
        double price = 9.99;        // 双精度浮点
        bool isReady = true;        // 布尔型
        char grade = 'A';           // 字符型
        decimal salary = 5000.50m;  // 高精度小数
        byte code = 0xFF;           // 字节类型

        // 引用类型
        string name = "ChatGPT";                     // 字符串
        int[] numbers = { 1, 2, 3 };                 // 数组
        object obj = new { Id = 1, Name = "Test" };  // 匿名对象
        dynamic dynamicVar = "可改变类型";           // 动态类型

        // 自定义类型
        Point p = new Point { X = 10, Y = 20 };  // 结构体实例
        Status state = Status.Active;            // 枚举实例
        var person = new { Age = 30 };           // 匿名类型
    }
}
```


# 布尔运算

| 运算符  | 名称 | 描述                        |
| ---- | -- | ------------------------- |
| &&   | 与  | 两操作数均为\`true\`时返回\`true\` |
| \|\| | 或  | 任意操作数为\`true\`时返回\`true\` |
| !    | 非  | 反转布尔值 \`!true\`→\`false\` |

# 分支语句

```c# title="分支语句：if"
if (条件1)
{
    // 条件1为 true 时执行
}
else if (条件2)
{
    // 条件2为 true 时执行
}
else
{
    // 所有条件均不满足时执行
}

```


```c# title="分支语句：Switch"
string day = "Monday";
switch (day)
{
    case "Monday":
        Console.WriteLine("工作日");
        break;
    case "Saturday":
    case "Sunday":
        Console.WriteLine("周末"); // 合并多个 case
        break;
    default:
        Console.WriteLine("未知");
        break;
}

```


```c# title="三元运算符"
int age = 18;
string status = (age >= 18) ? "成年人" : "未成年人";

var result = condition ? valueIfTrue : valueIfFalse; //语法
             
```


## 循环

```c# title="for循环"
//语法
for (初始化; 条件; 迭代)
{
    // 循环体
}

//示例
// 打印 0 到 4
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}

```


```c# title="while 循环"
//语法
while (条件)
{
    // 循环体
}


//示例
// 打印 0 到 4
int count = 0;
while (count < 5)
{
    Console.WriteLine(count);
    count++;
}

```


```c# title="do-while 循环（至少执行一次循环体）"
//语法
do
{
    // 循环体
} while (条件);

//示例
// 至少执行一次，直到输入 "exit"
string input;
do
{
    Console.Write("请输入指令：");
    input = Console.ReadLine();
} while (input != "exit");


```


```c# title="foreach 循环"
//语法
foreach (类型 变量 in 集合)
{
    // 循环体
}

//示例
// 遍历数组元素
int[] numbers = { 1, 2, 3 };
foreach (int num in numbers)
{
    Console.WriteLine(num);
}

```


```c# title="循环控制语句break continue"
//break立即终止当前循环，跳出循环体
for (int i = 0; i < 10; i++)
{
    if (i == 5) break; // 当 i=5 时终止循环
    Console.WriteLine(i);
}

//continue跳过本次循环剩余代码，直接进入下一次迭代
for (int i = 0; i < 5; i++)
{
    if (i == 2) continue; // 跳过 i=2 的循环体
    Console.WriteLine(i);
}
// 输出：0, 1, 3, 4


```
