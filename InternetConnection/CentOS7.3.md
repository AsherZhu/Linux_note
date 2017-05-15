### CentOS7.3

#### 开启网卡打开DHCP自动获取IP

1.查看网卡信息
> ip add

返回以下信息

```$xslt
1:lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN qlen 1
      link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
      inet 127.0.0.1/8 scope host lo
      valid_lft forever preferred_lft forever
      inet6 ::1/128 scope host
      valid_lft forever preferred_lft forever
2:ens33: <N0-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc pfifo_fast state DOWN qlen 1000
      link/ether 00:0c:29:c4:d1:bc brd ff :ff :ff :ff :ff :ff
```
**ens33**这个是本地网卡的名字，最后一行 **00:0c:29:c4:d1:bc** 是网卡的MAC地址 'Linux一切皆文件'

2.配置网卡开启网络连接
>cd /etc/sysconfig/network-scripts/ #进入网络配置文件目录<br>
vi ifcfg-ens33 #编辑配置文件
```$xslt
HWADDR=00:0c:29:c4:d1:bc
TYPE=Ethernet
BOOTPROTO=dhcp
DEFROUTE=yes
PEERDMS=yes
PEERROUTES=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUT0C0NF=yes
IPV6_DEFR0UTE=yes
IPV6_PEERDNS=yes
IPV6_PEERR0UTES=yes
IPV6_FAILURE_FATAL-no
IPV6_ADDR_GEN_M0DE=stable-privacy
NAME=ens33
UUID =27ed825-7c36-4145-94fb-ab71c4b45352
DEUICE=ens33
ONBOOT=yes

"ifcfg-ens33" 17L, 309C
```
>ps:以上增加了 "HWADDR=00:0c:29:c4:d1:bc" MAC地址<br>
"ONBOOT=no" 改为 "ONBOOT=yes"开启自动网络连接 

>:wq！#保存退出

>service network restart #重启网络服务

```$xslt
[root@localhost network-scripts18 service network restart
Restarting network (via systemctl):                            [ OK ]
```
