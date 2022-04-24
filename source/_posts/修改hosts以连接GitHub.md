---
title: 修改hosts以连接GitHub
date: 2020-07-19 15:24:14
categories: 小技巧
tags: GitHub
---

# 修改hosts以连接Github

当使用git克隆仓库时可能出现443: Time out的错误，用浏览器访问GitHub也不行时，可能的解决办法是修改hosts文件。

## 查询IP地址

首先在https://www.ipaddress.com/上查询github.com和github.global.ssl.fastly.net的IP地址（可能会发生变化）。

现在查到github.com的IP地址为140.82.114.3，github.global.ssl.fastly.net的IP地址为199.232.69.194。

## 修改hosts

在C:\Windows\System32\drivers\etc目录下的hosts文件中增加以下两行：

```
140.82.114.3 github.com
199.232.69.194 github.global.ssl.fastly.net
```

## 清除DNS缓存

修改完hosts需要清除DNS缓存：

![](https://i.loli.net/2020/07/19/qauIFXiAcGOCwyl.png)

执行以上步骤后，可能就已经能连接上GitHub了。