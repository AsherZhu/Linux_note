#### install TeamSpeak 3.0.0 Server | Linux


#### Update
> sudo apt-get update
 
#### Setup  [Server DownLoad](https://www.teamspeak.com/downloads.html#server "NEW URL")
32bit
> wget http://teamspeak.gameserver.gamed.de/ts3/releases/3.0.13.6/teamspeak3-server_linux_x86-3.0.13.6.tar.bz2

64bit
> wget http://teamspeak.gameserver.gamed.de/ts3/releases/3.0.13.6/teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2

> tar -vxjf teamspeak3-server_linux_amd ...

> cd teamspeak3-server_linux_amd ...

> ./ts3server_startscript.sh start
 
#### Auto Start Script
> cd /etc/init.d

> sudo vim ts3

> \#! /bin/bash<br>
 cd /.../teamspeak3-server_linux...<br>
 ./ts3server_startscript.sh start

> sudo chmod +x /etc/init.d/ts3

> sudo update-rc.d ts3 defaults

 
#### Other Commands
> ./ts3server_startscript.sh restart

> ./ts3server_startscript.sh stop

> ./ts3server_startscript.sh status

 
#### Ports
>9987 UDP (Voice)

>10011 TCP (Server Query)

>30033 TCP (File Server)

 
#### Notes
The command `sudo update-rc.d` ts3 defaults may return a warning. This is to be expected.
After a restart the command `./ts3server_startscript` status may show that the server is dead. This is a bug and the server is online.
Making the auto startup script can break your Ubuntu install. Please double check your commands before restarting the server.
