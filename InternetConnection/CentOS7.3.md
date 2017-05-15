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

