## 处理Linux运行java -jar中文出现乱码的问题
运行locale命令看一下结果：
```$xslt
LANG=C
LANGUAGE=C:
LC_CTYPE="C"
LC_NUMERIC="C"
LC_TIME="C"
LC_COLLATE="C"
LC_MONETARY="C"
LC_MESSAGES="C"
LC_PAPER="C"
LC_NAME="C"
LC_ADDRESS="C"
LC_TELEPHONE="C"
LC_MEASUREMENT="C"
LC_IDENTIFICATION="C"
LC_ALL=
```
#### 几个主要变量的意思：
1. LC_COLLATE：定义该环境的排序和比较规则
2. LC_CTYPE：用于字符分类和字符串处理，控制所有字符的处理方式，包括字符编码，字符是单字节还是多字节，如何打印等。是最重要的一个环境变量。
3. LC_MONETARY：货币格式
4. LC_NUMERIC：非货币的数字显示格式
5. LC_TIME：时间和日期格式
6. LC_MESSAGES：提示信息的语言。另外还有一个LANGUAGE参数，它与LC_MESSAGES相似，但如果该参数一旦设置，则LC_MESSAGES参数就会失效。LANGUAGE参数可同时设置多种语言信息，如
LANGUANE=”zh_CN.GB18030:zh_CN.GB2312:zh_CN”。
7. LANG：LC_*的默认值，是最低级别的设置，如果LC_*没有设置，则使用该值。类似于 LC_ALL。
8. LC_ALL：它是一个宏，如果该值设置了，则该值会覆盖所有LC_*的设置值。注意，LANG的值不受该宏影响。

#### 解决方法：

把LC_CTYPE修改为“zh_CN.UTF-8”：
> cd

> vim .bashrc

添加：
```$xslt
export LANG='POSIX'
export LC_CTYPE='zh_CN.UTF-8'
```
生效：
> source .bashrc

再次运行 locale

```$xslt
LANG=POSIX
LANGUAGE=C:
LC_CTYPE=zh_CN.UTF-8
LC_NUMERIC="POSIX"
LC_TIME="POSIX"
LC_COLLATE="POSIX"
LC_MONETARY="POSIX"
LC_MESSAGES="POSIX"
LC_PAPER="POSIX"
LC_NAME="POSIX"
LC_ADDRESS="POSIX"
LC_TELEPHONE="POSIX"
LC_MEASUREMENT="POSIX"
LC_IDENTIFICATION="POSIX"
LC_ALL=
```
已经生效了

如果报错 ：`-bash: warning: setlocale: LC_CTYPE: cannot change locale (zh_CN.UTF-8)`

则需要重新安装中文语言包 

执行下面命令
> sudo apt-get -y install language-pack-zh-hans

或
> sudo apt-get -y install language-pack-zh-hans language-pack-zh-hans-base

如果想支持繁体字，则执行
> sudo apt-get -y install language-pack-zh-hant

或
> sudo apt-get -y install language-pack-zh-hant language-pack-zh-hant-base
