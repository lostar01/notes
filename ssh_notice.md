SSH Some Config
```
#ssh tunnel
##将远程主机或者socket ，转发并监听到本地
在HostA 上运行：
暴露HostB端口到HostA
ssh -CNL HostA:portA:HostB:portB Buser@HostB -p 22
暴露HostC端口到HostA
ssh -CNL HostA:portA:HostC:portC Buser@HostB -p 22

##将本端端口或者socket，转发并监听在远程主机
在HostB运行：
暴露HostB端口到HostA
ssh -CNR portA:HostB:portB UserA@HostA -p 22
暴露HostC端口到HostA
ssh -CNR portA:HostC:portC UserA@HostA -p 22

##在HostB上运行：
ssh -CND HostB:portB UserA@HostA -p 22
在HostC上可通过socket上网
curl --socks5 HostB:portB www.baidu.com

```
