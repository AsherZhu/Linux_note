## Linux Command
#### Update & upgrade & Install & remove
未授权root权限的用户需要在`apt-get`前面加 `sudo` 
> apt-get update 

> apt-get upgrade

> apt-get Install appName

> apt-get remove appName

> wget url `下载程序压缩包到当前目录`

> tar xvf fileName `解压缩程序到当前目录`

> dpkg --get-selections | grep appName `相关软件安装信息`

#### Directory Operation
> mkdir dirName1 dirName2 dirName3 `创建单个或者多个目录`

> rmdir dirName1 dirName2 dirName3 `删除单个或者多个目录`

如果文件非空的话用以下命令删除<br>

>rm -rf dirName `-r 向下递归` `-f 直接强行删除`

> cd dirName\dirName `指定进入目录下`

#### program

> ps -ef `查询正在运行的进程`

> kill -s 9 PID `杀死进程`

