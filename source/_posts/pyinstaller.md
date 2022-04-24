---
title: pyinstaller
date: 2020-06-08 20:48:51
categories: 小技巧
tags: pyinstaller

---

#  pyinstaller打包pyqt5程序

## 参数

> -D: 生成一个文件夹，里面有很多依赖库（默认参数，建议使用）
> -F: 仅生成一个.exe程序（除了程序非常简单，不建议使用）
> -w: 运行.exe程序时不显示cmd窗口
> -c: 图标路径，作为程序icon
> -p: 增加程序依赖文件

## 流程

假设要打包一个main.py，有一个依赖文件UartHelper.py，建议流程如下：

```
pyinstaller main.py -p UartHelper.py
```

或

```
pyinstaller main.py -D -p UartHelper.py
```

一般第一次都不会成功，在cmd运行dist/main目录下的main.exe。由于没有使用-w参数，可以看到报错信息：

![](https://i.loli.net/2020/06/08/ABmVxGthr6PUOsa.png)

这里报错：unable to find Qt5Core.dll on PATH，将dist/main目录下的Qt5Core.dll复制到dist/main/PyQt5/Qt/bin目录。再次运行，运行成功：

![](https://i.loli.net/2020/06/08/rExKD3SYmohBaQ6.png)

接下来可以使用-w参数使程序运行时不产生cmd窗口，生成后仍然需要复制Qt5Core.dll文件：

```
pyinstaller main.py -w -p UartHelper.py
```

最后双击运行dist/main目录下的main.exe：

![](https://i.loli.net/2020/06/08/7pft1sQP9neE5xg.png)

打包成功！