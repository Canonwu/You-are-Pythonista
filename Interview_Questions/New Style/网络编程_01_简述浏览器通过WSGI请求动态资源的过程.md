# 网络编程_01_简述浏览器通过WSGI请求动态资源的过程?

## Question
简述浏览器通过 WSGI 请求动态资源的过程?

浏览器发送的请求被 Nginx 监听到，Nginx 根据请求的 URL 的 PATH 或者后缀把请求静态资源的分发到静态资源的目录，别的请求根据配置好的转发到相应端口。
实现了 ____ 的程序会监听某个端口，监听到 ____ 转发过来的请求接收后(一般用 socket 的recv 来接收 HTTP 的报文)以后把请求的报文封装成`environ`的字典对象，然后再提供一个`start_response`的方法。把这两个对象当成参数传入某个方法比如`wsgi_app(environ, start_response)`或者实现了`__call__(self, environ, start_response)`方法的某个实例。这个实例再调用`start_response`返回给实现了____ 的中间件，再由中间件返回给 ____。

%!A. WSGI, Nginx, WSGI, Nginx!%

%!B. Nginx, WSGI, Nginx, WSGI!%

%!C. WSGI, WSGI, Nginx, Nginx!%

%!D. Nginx, Nginx, WSGI, WSGI!%

----

## Answer
@!A!@

----

## Analysis

浏览器发送的请求被 Nginx 监听到，Nginx 根据请求的 URL 的 PATH 或者后缀把请求静态资源的分发到静态资源的目录，别的请求根据配置好的转发到相应端口。
实现了 WSGI 的程序会监听某个端口，监听到 Nginx 转发过来的请求接收后(一般用 socket 的recv 来接收 HTTP 的报文)以后把请求的报文封装成`environ`的字典对象，然后再提供一个`start_response`的方法。把这两个对象当成参数传入某个方法比如`wsgi_app(environ, start_response)`或者实现了`__call__(self, environ, start_response)`方法的某个实例。这个实例再调用`start_response`返回给实现了WSGI 的中间件，再由中间件返回给 Nginx。