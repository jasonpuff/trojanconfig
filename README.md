# trojanconfig
config your trojan, change your trojan port

Trojan工作在443端口，并且处理来自外界的HTTPS请求，如果是合法的Trojan请求，那么为该请求提供服务，否则将该流量转交给web服务器Nginx，由Nginx为其提供服务。基于这个工作过程可以知道，Trojan的一切表现均与Nginx一致，不会引入额外特征，从而达到无法识别的效果。当然，为了防止恶意探测，我们需要将80端口的流量全部重定向到443端口，并且服务器只暴露80和443端口，这样可以使得服务器与常见的Web服务器表现一致。

修改trojan工作端口，需要先找到Trojan的config文件

文件位置 /usr/local/etc/trojan

trojan的config文件修完完成以后需要重新系统Trojan
命令

sudo systemctl restart trojan  
重启trojan

sudo systemctl status trojan
查看Trojan运行状态


建议端口 

1）注册端口（Registered Ports）：端口号从1024到49151。它们松散地绑定于一些服务。也是说有许多服务绑定于这些端口，这些端口同样用于许多其他目的。这些端口多数没有明确的定义服务对象，不同程序可根据实际需要自己定义，如后面要介绍的远程控制软件和木马程序中都会有这些端口的定义的。记住这些常见的程序端口在木马程序的防护和查杀上是非常有必要的。常见木马所使用的端口在后面将有详细的列表。
2）动态或私有端口（Dynamic and/or Private Ports）：端口号从49152到65535。理论上，不应把常用服务分配在这些端口上。实际上，有些较为特殊的程序，特别是一些木马程序就非常喜欢用这些端口，因为这些端口常常不被引起注意，容易隐蔽。
