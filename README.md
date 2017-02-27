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


更多命令，请输入./ngrok  --help 查看！！！ 官网：http://www.ngrok.org

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
