#为畅言平板中应用“写字无忧”提供跳转浏览任意网页提供思路

要求：

1、该思路需要借助可以使用无线网络访问互联网的计算机，且计算机具备开启移动热点的功能

2、该思路仅为处于学校之中、学生使用具有限制自由访问网络的平板电脑下提出的设想。

思路：

1、在任意可访问互联网、可开启移动热点的计算机中编辑系统hosts文件，使任意设备在连接至计算机并请求特定域名时解析到计算机本地或其他域名

以Windows系统为例：（hosts文件位于C:\Windows\System32\drivers\etc下）

....前略....
# localhost name resolution is handled within DNS itself.
#	127.0.0.1       localhost
#	::1             localhost

#在此处写下需要本机ip地址（即需要转发至的地址）与触发转发条件的请求域名
#以下一行意为：当连接到此计算机热点的设备请求www.example.com时都会被解析至192.168.31.22:80

192.168.31.22 www.example.com
  
# To allow the same kube context to work on the host and the container:
127.0.0.1 kubernetes.docker.internal
# End of section


2、在计算机上安装服务器软件。在此以VSCode文本编辑器下的live-server插件为例

编辑配置文件端口为80

在html网页下目录开启服务


3、平板电脑连接至计算机无线热点，以“写字无忧”软件为例：点按“QQ登录”按钮→点按“反馈建议”按钮，如果不出意外会进入跳转网页了。
