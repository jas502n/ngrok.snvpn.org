# ngrok.snvpn.org





 ==========================================================================

                                            Shaoyu-Ngrok客户端启动工具

                                            作者: Shaoyu QQ：1126179674

                                            官方QQ群：397467063

                                            官网：www.snvpn.org

                                            作者博客：www.90xss.cn

                      ==========================================================================

==========================================================================

1.首先新建一个ngrok.config文件,里面写入服务器的ngrok的地址
server_addr: ngrok.snvpn.org:4443
trust_host_root_certs: false

2.给ngrok客户端可执行权限，chmod 777 ngrok ,就可以加上命令运行ngrok

Example: ./ngrok -subdomain server  -proto=http -config=ngrok.config 80

==========================================================================


更多命令，请输入./ngrok  --help 查看！！！ 官网：http://www.ngrok.com

Usage: ./ngrok [OPTIONS] <local port or address>
Options:
  -authtoken="": Authentication token for identifying an ngrok.com account
  -config="": Path to ngrok configuration file. (default: $HOME/.ngrok)
  -hostname="": Request a custom hostname from the ngrok server. (HTTP only) (requires CNAME of your DNS)
  -httpauth="": username:password HTTP basic auth creds protecting the public tunnel endpoint
  -log="none": Write log messages to this file. 'stdout' and 'none' have special meanings
  -log-level="DEBUG": The level of messages to log. One of: DEBUG, INFO, WARNING, ERROR
  -proto="http+https": The protocol of the traffic over the tunnel {'http', 'https', 'tcp'} (default: 'http+https')
  -subdomain="": Request a custom subdomain from the ngrok server. (HTTP only)

Examples:
	ngrok 80
	ngrok -subdomain=example 8080
	ngrok -proto=tcp 22
	ngrok -hostname="example.com" -httpauth="user:password" 10.0.0.1
	
==========================================================================
同时转发多个TCP端口配置文件ngrok.config

server_addr: "ngrok.snvpn.org:4443"
trust_host_root_certs: false
tunnels:
  myport:
    remote_port: 12345
    proto:
      tcp: 22

  mytest:
    remote_port: 22222
    proto:
      tcp: 888
 
========================================================================== 
  这里要注意空格，是以2个空格为一个缩进，一个是tcp名字叫myport,另外一个叫mytest
  
  客户端启动命令 ./ngrok  -config=ngrok.config start myport mytest
  
  执行以后就能看到同时映射2个tcp端口到ngrok.snppn.org上了。
  都是指定端口12345   22222                                                                                                                ==========================================================================                                                               ngrok
																   
Tunnel Status                 online                                                                                     
Version                       1.7/1.7                                                                                     
Forwarding                    tcp://ngrok.snvpn.org:22222 -> 127.0.0.1:888                                               
Forwarding                    tcp://ngrok.snvpn.org:12345 -> 127.0.0.1:22                                                 
Web Interface                 127.0.0.1:4040                                           
# Conn                        0   
Avg Conn Time                 0.00ms  


