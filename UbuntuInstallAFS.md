## Ubuntu Install ArchiSteamFarm

---

#### [ArchiSteamFarm](https://github.com/JustArchi/ArchiSteamFarm/)

&emsp;&emsp;ASF是一个C＃应用程序，允许您同时使用多个Steam帐户来获取steam卡片。ASF不需要任何Steam客户端在后台运行，不会启动任何额外的流程，并立即处理所添加的的Steam帐户。除此之外，它还可以在服务器或其他无桌面计算机上运行，​​并具有完整的跨操作系统支持，可以在任何支持.NET Core的操作系统上启动，例如Windows，Linux或OS X。<br>
&emsp;&emsp;ASF不要求也不会以任何方式干扰Steam客户端。除此之外，它不要求独占访问给定的帐户，这意味着您可以在Steam客户端使用您的主帐户，并使用ASF同时空闲同一个帐户。如果您决定启动游戏，则ASF将断开连接，并在完成游戏后恢复空闲状态，并在整个过程中尽可能透明。

---

#### 核心功能
* 使用任意数量的活动帐户自动空闲可用的游戏卡
* 没有要求运行，甚至没有安装官方的Steam客户端
* 保证无VAC
* 复杂的错误报告机制，使ASF变得更加智能，即使在出现Steam或网络问题的情况下也能恢复空闲状态
* 可定制的卡片空闲算法，尽可能提高掉落卡片的效率
* 脱机怠速，让您跳过游戏状态，并停止混淆你的朋友
* 先进的支持ALT帐户，包括赎回钥匙，赎回礼品，接受交易和更多通过简单的蒸汽聊天的能力
* 支持最新的Steam安全功能，包括SteamGuard，SteamParental和双因素身份验证
* 独特的ASF 2FA机制，允许ASF充当移动认证者（如果需要的话）
* StreamTradeMatcher集成，允许ASF通过接受欺诈交易来帮助您完成您的蒸汽徽章
* 基于.NET Core 2.0，跨OS兼容性，对Windows，Linux和OS X的官方支持
* ...还有很多！

---

#### 设置/帮助
&emsp;&emsp;关于设置和使用ASF的详细指导可以在我们的wiki的[设置](https://github.com/JustArchi/ArchiSteamFarm/wiki/Setting-up)部分中找到。

---

#### 兼容性/支持的操作系统
&emsp;&emsp;ASF正式支持Windows，Linux和OS X操作系统。请访问wiki上的[兼容性](https://github.com/JustArchi/ArchiSteamFarm/wiki/Compatibility)部分了解更多信息。

---

#### 想知道更多？
&emsp;&emsp;我们的[wiki](https://github.com/JustArchi/ArchiSteamFarm/wiki)包括许多其他文章，可以帮助您进一步使用ASF，并向您展示您可以使用的所有内容。

---

## 简述安装教程

1. 需要安装.net运行环境，因为不同linux发行版安装略有差异，所以我们需要最权威的微软官网教程[Prerequisites for .NET Core on Linux](https://docs.microsoft.com/en-us/dotnet/core/linux-prerequisites?tabs=netcore2x#tabpanel_-r1y2MrINK_netcore2x)，这里我们要安装的是.NET Core 2.0。
2. 开始安装ASF
   1. 在作者[GitHub](https://github.com/JustArchi/ArchiSteamFarm/releases)下载对应版本的ASF.zip。`下面我就用我写下这篇笔记时的最新版为例`
      > wget https://github.com/JustArchi/ArchiSteamFarm/releases/download/3.0.4.7/ASF-linux-x64.zip
   2. 解压缩到文件夹
      > unzip ./ASF-linux-x64.zip -d /root/application/ASF-linux-x64/
   3. cd进解压缩的目录
      > cd /root/application/ASF-linux-x64/
   4. 修改权限
      > chmod +x ArchiSteamFarm
   5. 配置ASF,通过官方给的链接生成bot文件：[ASF Config Generator](https://justarchi.github.io/ArchiSteamFarm/#/bot)<br>
   在Name中输入配置文件的名字，注意使用英文不要加空格<br>
   `SteamLogin中`输入steam账号id<br>
   `SteamPassword`中输入steam密码<br>
   `Enabled选`√<br>
   `IsBotAccount`选×<br>
   点击`Download`就会下载一个和Name名字一样的.json文件<br>
   将文件通过FTP上传到`/root/application/ASF-linux-x64/config/`<br>
   6. 进入`ASF-linux-x64`目录
      > cd /root/application/ASF-linux-x64/
   7. 执行`./ArchiSteamFarm`启动ASF
      > ./ArchiSteamFarm
      
      如果开启了手机令牌，会提示输入令牌验证码