---
title: chocolatey
date: 2020-03-23 18:08:56
categories: 小技巧
tags: chocolatey

---

# Windows包管理器chocolatey的安装与使用

## 安装

以管理员身份运行cmd，输入：

```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

## 使用chocolatey安装make

```
choco install make
```

安装成功：

```
C:\Users\WenQinghua\Desktop>choco install make
Chocolatey v0.10.15
Installing the following packages:
make
By installing you accept licenses for the packages.
Progress: Downloading make 4.3... 100%

make v4.3 [Approved]
make package files install completed. Performing other installation steps.
 ShimGen has successfully created a shim for make.exe
 The install of make was successful.
  Software install location not explicitly set, could be in package or
  default install location if installer.

Chocolatey installed 1/1 packages.
 See the log for details (C:\ProgramData\chocolatey\logs\chocolatey.log).

C:\Users\WenQinghua\Desktop>make
make: *** No targets specified and no makefile found.  Stop.

C:\Users\WenQinghua\Desktop>make -v
GNU Make 4.3
Built for Windows32
Copyright (C) 1988-2020 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
```

