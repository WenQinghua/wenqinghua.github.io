---
title: Win10关闭占用某一端口的进程
date: 2020-07-23 21:38:12
categories: 小技巧
tags: win10
---

# Win10关闭占用某一端口的进程

## 查看端口占用情况

```bash
netstat -ano | findstr 端口号
```

## 关闭该进程

### 使用任务管理器关闭

根据PID找到该进程，结束任务

## 使用命令关闭

```bash
taskkill -PID 进程号 -F
```

