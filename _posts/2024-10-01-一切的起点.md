---
layout:     post
title:      "一切的起点"
subtitle:   " 扉不有初，鮮克有終。 "
date:       2025-08-7 20:00:00
author:     "Xiangmin Li"
header-img: "img/post-bg-2015.jpg"
catalog: true
#tags:
---

# 开始C#编程语言的学习

大概在三四年前，我萌生了一个想法：做游戏！

如今，终于是安稳了一些，使我可以着手去实现它了．

这里，大概就是梦的起点了吧．

## 第一步

开发游戏的第一步，毫无疑问是掌握**C#编程语言**以及**Unity引擎的用法**

当然在这之前，还要具备计算机的基础知识: 
>**离散数学** <br>**线性代数** <br>**操作系统** <br>**计算机网络**<br>**计算机组成原理**<br>**数据结构**<br>**软件工程**

准备好以上的知识储备后, 就是紧张刺激的编程学习了

## 方向和方法

学习一门编程语言的第一步, 自然是了解它的全景图, C#是一门编程语言, 但它不仅仅是语言, 除了代码这种用来描述逻辑的形式语言外, 还有它的运行环境以及编译过程. 

C#的运行环境被称为CLR, C#源代码经过csc编译器成为IL中间语言,然后在CLR和JIT的共同作用下进一步被解释或编译为机器码成为CPU可执行的指令. 

正是由于CLR的存在, 使得C#语言可以在多平台上运行, CLR还提供GC自动回收垃圾, 异常处理等较为先进的功能, 所以说,C#是一门高级语言, 学习C#是要比C要难一些. 

C#是支持面向对象思想的, 面向对象OOP思想是一个比较抽象的代码组织思想, 想要熟练掌握它, 搞不好是需要成千上万小时的敲代码来磨炼, 有人说, 编程是一门手艺, 既然是手艺那就需要大量的练习来刷熟练度, 这是没有捷径可走的, 干就完了. 

## 开发文件结构

``` 
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

