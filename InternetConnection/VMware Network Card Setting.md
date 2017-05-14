#Linux系统VMware桥接上网的方法
在安装部署VMware虚拟机时，常常需要用到桥接模式上网。<br>
核心有两个部分：

###第一
在VMware中的【虚拟网络编辑器】中添加一个网络，定义为桥接模式，也就是虚拟网络编辑器--桥接模式--桥接到【自动】。

###第二
16设置虚拟机使用刚才创建的桥接器，依次打开【虚拟机】--【设置】--【网络适配器】

Linux系统VMware桥接上网的方法

1. 打开虚拟网络编辑器。<br>
<img src="https://github.com/ZhuShuai1992/Linux_Study/blob/master/InternetConnection/image/1.jpg?raw=true">
2.这里是安装虚拟机后自动生成的网络配置，点击移除。<br>
<img src="https://github.com/ZhuShuai1992/Linux_Study/blob/master/InternetConnection/image/2.jpg?raw=true">