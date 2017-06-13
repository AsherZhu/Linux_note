#### 一、sudo apt-get update 和 sudo apt-get upgrade 出错：（Ubuntu更新过程被中断后的问题）

Ubuntu的更新过程是先下载完源里的文件就开始执行升级，如果涉及到一些因为版权或是其他问题没加入源的文件，在升级安装的中途再从第三方服务器上下载。有时需要下载的文件比较大，而网速又不给力，就会在这里耽搁很久。万一有特殊情况必须关机，那么更新就会被中断。这就会带来一点的问题。

首先一个就是当你再次使用“更新管理器”更新的时候，会提示你：<br>
E: Could not get lock /var/lib/dpkg/lock - open (11: Resource temporarily unavailable)<br>
`E: 无法获得锁 /var/lib/dpkg/lock - open (11: Resource temporarily unavailable)`<br>

E: Unable to lock the administration directory (/var/lib/dpkg/), is another process using it?<br>
`E: 无法锁定管理目录(/var/lib/dpkg/)，是否有其他进程正占用它?`


解决方法：
> sudo rm /var/cache/apt/archives/lock

> sudo rm /var/lib/dpkg/lock

这个问题解决了，还有可能会出现使用`apt-get`或者`dpkg`时无法更新或者安装软件。提示使用`sudo dpkg --configure -a`，但是还是无法解决。错误提示类似于`dpkg: error: parsing file '/var/lib/dpkg/updates/0073' near line 0:`，也就是`/var/lib/dpkg/updates/`目录下的某个文件出了问题。解决办法就是删掉该目录下的所有文件。

另：解决方法：
`sudo rm /var/lib/dpkg/updates/`资料夹里面的档案有问题，使的更新软件出现错误，所以把它完全删除，下面的指令会重新建立
> sudo apt-get update `更新可下载应用明细`

> sudo apt-get upgrade `根据以上明细升级应用`

#### 二、sudo apt-get update出现问题

`E:Encountered a section with no Package: header, E:Problem with MergeList /var/lib/apt/lists/cn.archive.ubuntu.com_ubuntu_dists_natty_main_binary-i386_Packages`
终端中输入以下两条命令：
> sudo rm /var/lib/apt/lists/* -vf

> sudo apt-get update

#### 三.另一个问题的解决办法

`An error occurred. Please run Package Manager from the right-click menu or apt-get from a terminal to see what is wrong.`<br>
`The error message was: 'Error: BrokenCount > 0'. This usually means that your installed packages have unmet dependencies.`
> sudo bash

> apt-get clean

> cd /var/lib/apt

> mv lists lists.old

> mkdir -p lists/partial

> apt-get clean

> apt-get update

[转修改自](http://www.cnblogs.com/cj2014/p/4688137.html "sudo apt-get upgrade 不成功遇到问题")