# ApkTools for Mac

在本文中我将介绍如何在Mac OS X上使用apktool.jar、dex2jar、jd-gui来进行apk的反编译和查看源码。下面会提供每个工具的下载地址。

测试环境:OS X EI Capitan 10.11.4

### 1.下载脚本

右键[这里](https://link.jianshu.com?t=https://raw.githubusercontent.com/iBotPeaches/Apktool/master/scripts/osx/apktool),把它存储命名为apktool，记得不要带后缀，要把后缀去除。

### 2.下载apktool.jar

点击下载[apktool.jar](https://link.jianshu.com?t=https://bitbucket.org/iBotPeaches/apktool/downloads),目前最新的版本为2.0.3。多说一句，尽量下载最新版本，因为它支持的Android版本越高。

下载完成后重命名为apktool.jar

### 3.创建文件夹

在桌面创建文件夹命名为apktool,把apktool.jar和apktool放进去。

### 4.配置apktool

(1)打开终端,输入:

cd /usr/local/bin
`</pre>

如果电脑不存在这个目录，那么创建一个:

<pre>`sudo mkdir bin
`</pre>

创建完成后再使用cd命令看看。

(2)打开终端，使用cd命令定位到apktool文件夹:

<pre>`cd Desktop/apktool/
`</pre>

使用cp命令把apktool.jar和apktool文件拷贝到/usr/local/bin

<pre>`sudo cp apktool.jar apktool /usr/local/bin
`</pre>

之后,使用

<pre>`sudo apktool
`</pre>

可以查看apktool的版本

(3)现在可以使用apktool相关命令了,和windows是一样的。

把apk文件放到apktool文件夹,然后回到apktool文件夹下:

<pre>`cd /Desktop/apktool/
`</pre>

使用(xxx.apk是你的apk名字)

<pre>`apktool d xxx.apk
`</pre>

就能进行反编译了。对于系统apk，需要额外导入框架才能反编译。更多apktool命令可以自行百度Google。

### 5.配置dex2jar

(1)下载[dex2jar](https://link.jianshu.com?t=http://mac.softpedia.com/get/Developer-Tools/dex2jar.shtml),解压

(2)将dex2jar文件夹放在apktool文件夹下

(3)把apk文件解压,可以直接解压或者修改后缀.zip再解压,找到classes.dex文件，把它放进dex2jar文件夹下

(4)定位到dex2jar文件夹(不同版本的dex2jar文件名不同,请作相应替换):

<pre>`cd Desktop/apktool/dex2jar-0.0.9.15/
`</pre>

执行命令:

<pre>`sh dex2jar.sh classes.dex

这时会在dex2jar文件夹下生成一个classes_dex2jar.jar文件。

### 6.查看java源码

下载[jd-gui](https://link.jianshu.com?t=http://mac.softpedia.com/get/Development/Java/JD-GUI.shtml),将下载的jd-gui压缩包解压,然后右键上一步生成的classes_dex2jar.jar文件,选择打开方式-&gt;JD-GUI，就可以查看java源码了!
