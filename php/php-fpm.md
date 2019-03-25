# https://github.com/YuanLianDu/YLD-with-Php/blob/master/articles/php/php-fpm.md
# CGI:(Common Gateway Interface)
> 概述：CGI 是一种协议，描述的是服务器和请求处理程序之间传输数据的一种标准

> 原理：当需要请求使用网关资源时，服务器就会调起应用程序来处理请求
> CGI 弱点，每一个请求都会创建一个新的进程，所以，服务器和网关之间的分离会造成性能的耗费，会限制使用CGI的服务器的性能，并且会加重服务端机器资源的负担

# FastCgi 
> 可以说这是CGI的升级版，是一种让交互程序与Web服务器通信的协议，FastCGI致力于减少网页服务器与CGI程序之间互动的开销，从而使服务器可以同时处理更多的网页请求

> 如何增强：
>> FastCGI接口模拟了CGI，但FastCGI是作为持久守护进程运行的，消除了为每个请求建立或拆除新进程所带来的性能损耗。也就是允许，一个进程内可以处理多个请求。 也就说CGI解释器保持在内存中，并接受了FastCGI进程管理和调度，所以它可以提供更好的性能，可扩展性，故障切换等特点

> FastCGI 的工作原理
* Web Server 启动时载入FastCGI进程管理器
* FastCGI 进程管理器首先初始化自己，启动一批CGI解释器进程，然后等待来自Web Server的链接
* 当Web Server中的一个客户端请求达到时，FastCGI进程管理器会选择并链接一个CGI解释器，Web Server的CGI环境变量和标准输入会被送达FastCGI进程的PHP-CGI
* FastCGI子进程从同一连接完成返还给Web Server的标准输出和错误信息。当请求进程完成后，FastCGI进程会关闭此连接。FastCGI会等待并出来来自FastCGI进程管理器（运行在Web Server中的）的下一个连接。 在CGI模式，php-cgi然后会退出


# PHP-FPM 是一个php FastCGI管理器，是只用于PHP的
* FPM 的 master 进程接收到请求
* master 进程根据配置指派特定的worker进程进行请求处理，如果没有可用的进程，返回错误。这也是我们配合Nginx 遇到 502 错误比较多的原因
* worker 进程处理请求，如果超时，返回504错误
* 请求处理结束，返回结果