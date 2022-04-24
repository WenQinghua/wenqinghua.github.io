---
title: Servlet
date: 2020-07-27 16:56:05
tags: Servlet
categories: Java
---

# Servlet

## Servlet执行原理

> 1. 当服务器接收到客户端浏览器的请求后，会解析请求URL路径，获取访问的Servlet的资源路径。
>
> 2. 查找web.xml文件，是否有对应的<url-pattern>标签体内容。
> 3. 如果有，则再找到对应的<servlet-class>全类名。
> 4. tomcat会将字节码文件加载进内存，并且创建其对象。
> 5. 使用其方法。

## Servlet中的生命周期方法

- 被创建：执行init方法，只执行一次
  - 默认情况下，第一次被访问时，Servlet被创建
  - 在<servlet>标签下配置
    - 在第一次被访问时，创建：<load-on-startup>的值为负数
    - 在服务器启动时，创建：<load-on-startup>的值非负数
  - 多个用户同时访问时，可能存在线程安全问题
    - 解决办法：尽量不要在servlet中定义成员变量，即使定义了，也不要对其修改值
- 提供服务：执行service方法，执行多次
- 被销毁：执行destroy方法，只执行一次
  - 服务器正常关闭时，servlet被销毁之前执行，用来释放资源

