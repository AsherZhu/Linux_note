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

#### File

> vim fileName `新建文件`

> mv oldName newName `文件重命名`

#### Directory Operation
> mkdir dirName1 dirName2 dirName3 `创建单个或者多个目录`

> rmdir dirName1 dirName2 dirName3 `删除单个或者多个目录`

> rm -rf dirName `-r 向下递归` `-f 直接强行删除` `如果文件非空的话此命令删除`

> rm -rf fileName/* `递归删除 fileName下所有的文件&目录`

> cd dirName\dirName `指定进入目录下`

#### Program

> ps -ef `查询正在运行的进程`

> ctrl + z `将在前台执行的命令放到后台 并暂停`

> jobs `查看当前有多少在后台运行的命令`

> fg `将后台中的命令调至前台继续运行` `如果后台中有多个命令用 fg %jobnumber 通过job命令查询到的序列号（非PID）`

> bg `将一个在后台暂停的命令，变成继续执行` `如果后台中有多个命令用 fg %jobnumber`

> kill -s 9 PID `杀死进程`

#### Run

> nohup python run.py > botlog.log 2>&1 & `后台运行并且写入运行日志到.log文件`

> ./ArchiSteamFarm |tee -a /home/ubuntu/A_Log/ArchiSteamFarm.log `前台运行并且写入日志文件`

