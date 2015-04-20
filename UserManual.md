# zlevoclient Manual #

## 编译： ##
> 编译需要libpcap库，一般Linux发行版里面安装libpcap包即可，在ubuntu中如下：
```
sudo apt-get install libpcap-dev
```
> 然后从命令行进入源代码目录，运行make，应该很快就能生成zlevoclient，当然前提是系统中安装了gcc等编译环境，这里不再累赘。

> 如果需要静态编译libpcap库（这样无论目标运行系统有没有安装libpcap库、或者任何版本，都能正常认证），可以修改Makefile文件，把第二行LIBS = -lpcap改成LIBS = /usr/lib/libpcap.a

## 运行： ##
> 运行需要root权限，看例子即可：
```
sudo ./zlevoclient -u username -p password --background
```
> u、p、分别是用户名、密码，--background参数可让程序进入后台运行，具体可./zlevoclient --help
查看压缩包内提供了一个启动脚本zlevo\_run.sh。
用gedit等编辑软件修改sh文件内的username、password，以后运行sudo ./zlevo\_run.sh即可。

## 终止： ##
默认方式启动的程序，按Ctrl + C即可正常下线，程序终止。
若以后台方式启动后，可使用如下方式来终止程序：
```
sudo ./zlevoclient -l
```

出现如下提示:
```
&&Info: Kill Signal Sent to PID 2010.
```
成功下线。



**Another PT Work.**

**Blog**:  http://apt-blog.co.cc/

**GMail**: pentie # gmail.com

2009-05-20 于广州大学城