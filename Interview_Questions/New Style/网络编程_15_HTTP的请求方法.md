# 网络编程_15_HTTP的请求方法

## Question
以下关于 HTTP 请求方法说法错误的是（）？

%!A. HTTP1.0 定义了三种请求方法： GET， POST 和 HEAD 方法!%

%!B. GET 请求指定的页面信息，并返回实体主体!%

%!C. HEAD 请求返回的响应中有具体的内容，用于获取报头!%

%!D. OPTIONS 允许客户端查看服务器的性能!%

----

## Answer
@!C!@

----

## Analysis

根据 HTTP 标准，HTTP 请求可以使用多种请求方法。
HTTP1.0 定义了三种请求方法： GET， POST 和 HEAD 方法。
HTTP1.1 新增了五种请求方法：OPTIONS， PUT， DELETE， TRACE 和 CONNECT 方法。

1、GET 请求指定的页面信息，并返回实体主体。
2、HEAD 类似于 get 请求，只不过返回的响应中没有具体的内容，用于获取报头
3、POST 向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。POST 请求可能会导致新的资源的建立和/或已有资源的修改。
4、PUT 从客户端向服务器传送的数据取代指定的文档的内容。
5、DELETE请求服务器删除指定的页面。
6、CONNECT HTTP/1.1 协议中预留给能够将连接改为管道方式的代理服务器。
7、OPTIONS 允许客户端查看服务器的性能。
8、TRACE 回显服务器收到的请求，主要用于测试或诊断。