# trojanconfig
config your trojan, change your trojan port

Trojan工作在443端口，并且处理来自外界的HTTPS请求，如果是合法的Trojan请求，那么为该请求提供服务，否则将该流量转交给web服务器Nginx，由Nginx为其提供服务。基于这个工作过程可以知道，Trojan的一切表现均与Nginx一致，不会引入额外特征，从而达到无法识别的效果。当然，为了防止恶意探测，我们需要将80端口的流量全部重定向到443端口，并且服务器只暴露80和443端口，这样可以使得服务器与常见的Web服务器表现一致。

修改trojan工作端口，需要先找到Trojan的config文件

文件位置 /usr/local/etc/trojan

trojan 命令

sudo systemctl restart trojan  
重启trojan

sudo systemctl status trojan
查看Trojan运行状态
