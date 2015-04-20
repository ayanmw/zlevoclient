# zlevoclient 使用教程 #
# 注意 #
本教程假设您已经配置好您的静态ip地址了，如果不知道怎么配置静态ip，请google一下。

## 下载解压 ##
从[项目主页](http://code.google.com/p/zlevoclient/)下载最新的二进制包，下面以
zlevoclient-0.8-bin\_i386.tar.gz为例：
```
tar xvf zlevoclient-0.8-bin_i386.tar.gz
cd  zlevoclient-0.8-bin_i386
```

## 使用方法 ##
```
sudo  ./zlevoclient -u username -p password -b
```

如果您想使用启动脚本来运行，请参考下面的步骤：

## 启动脚本 ##
在目录中有一个自动运行的脚本，zlevo\_run.sh
现在假设大家用的是默认版本的ubuntu，系统里面有gedit编辑器：
```
gedit zlevo_run.sh
```
很明显大家看到一行
```
./zlevoclient -u username -p password -b
```
当然，就是改上你的用户名和密码了，保存。

## 运行认证 ##
回到终端下面：
```
sudo ./zlevo_run.sh
```
恩，会出现一系列类似如下的提示：
```
######## Lenovo Client ver. 0.8 #########
Device:     eth0
MAC:        00:e0:4d:23:cd:92
IP:         10.11.24.45
########################################
>>Protocol: SEND EAPOL-Start
>>Protocol: REQUEST EAP-Identity
>>Protocol: SEND EAP-Response/Identity
>>Protocol: REQUEST MD5-Challenge(PASSWORD)
>>Protocol: SEND EAP-Response/Md5-Challenge
>>Protocol: EAP_SUCCESS
&&Info: Authorized Access to Network. 
&&Info: ZlevoClient Forked background with PID: [11168]

>>Protocol: SEND EAPOL Keep Alive

```

**~~理论上~~现在你就能上网了！**

以后每次都进来这个目录，重复**运行认证**这个步骤，~~才~~就可以上网了！

## 能不能简单点 ##

~~靠，自己想办法啊~~

**能！**如果你按上面的步骤已经能用zlevoclient上网了，那么以后“一键上网”也不是什么难事：

首先，把zlevoclient，zlevo\_run.sh复制到/usr/local/bin/目录下：
```
sudo cp zlevoclient zlevo_run.sh /usr/local/bin/
```
然后编辑zlevo\_run.sh，在./zlevoclient -u username -p password -b之前添加一行：
```
cd /usr/local/bin/
```

最后在桌面新建一个启动器，名称自定，命令里面输入
```
gksu zlevo_run.sh
```

这样之后每次只需双击这个图标，或者把它拉到面板上面，单击，就出现一个密码窗口，输入密码就可以上网了！

**什么？你密码都不想输？行！**

```
sudo chmod 4755 /usr/local/bin/zlevoclient
```
然后启动器里面的gksu就可以去掉了，每次一点就上网！神奇吧！

甚至可以把zlevo\_run.sh加入到~/.bashrc文件里面，每次一进入桌面就自动连接上网，开了了吧！