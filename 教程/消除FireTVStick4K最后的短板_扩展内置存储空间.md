FireTV Stick 4K最大的短板是内置存储空间很小，而很多APK都需要安装在内置存储空间。
扩展空间的原因，主要是用于游戏APP。 需要的数据量很大, 一个游戏动不动就1-2G (程序+数据)。

在操作之前，建议先检查内置存储空间\Download目录下, 有通过手机或者其它方式安装软件时留下的APK原文件，这些都没有用了，可以删除，省下很多空间.

1. 需要OTG线，可以自制，或者买成品线。现在物流问题，成品线不好买，自制的话，可以看我这个帖.
   https://github.com/openwrt166/firetv/blob/master/%E6%95%99%E7%A8%8B/FireTV%20Stick%204K%E6%8A%98%E8%85%BE%E7%AC%AC%E4%BA%8C%E6%B3%A2%EF%BC%9A%E4%BA%B2%E5%AD%90%E6%B8%B8%E6%88%8F%E7%AF%87%EF%BC%88%E9%83%BD%E6%98%AF%E6%B5%8B%E8%AF%95%E8%BF%87%E7%9A%84%EF%BC%89.md

2. 主要操作是ADB. 有如下两种方式可选:
1) 首页教程里面说的，安装在FireTV Stick 4K上的Adb Remote Shell, 结合在手机上安装的FireTV APP输入命令。如果直接用遥控器输入命令会很累。
   2）电脑上安装ADB link来操作。ADBLink下载:  http://www.jocala.com/
      如果有电脑操作的话，安装APK、输入命令等比手机还是方便些。注意连接端口是5555。
   ![](D:\BX02\Desktop\09.png)

连接后，根据电视屏幕上的提示确认允许连接。
![](D:\BX02\Desktop\10.png)



3. FireTV Stick 4K 连接好OTG线，插上U盘，然后在ADB Shell 里面输入下面命令。

1）sm list-disks
会得到插入的U盘的名称. 我的是disk:8,0

2）第二步有两种选择.(根据自己的需求选择，U盘大选a,U盘小选b. 不管选哪个，U盘原有数据都会清除，请确认自己是否需要继续)
a. sm partition disk:8,0 mixed 50 (会把U盘分成两个同样大小的分区，一个作为内置存储的扩充（安装软件及保存软件数据)，一个作为外置存储（保存电影，图片等数据)
b. sm partition disk:8,0 private (会把整个U盘空间作为内置存储的扩充)
(上面的disk:8,0根据第1步得到的实际名称更改)

3) 做完这两步后,可以输入下面第4步的命令确认结果。以后新安装的程序，如果APP开发者在代码内有声明，会安装在扩充后的存储空间内。对于已经安装好的软件，可以用下面第4-6步命令转移到扩充后的存储空间内.

4) df -h 得到你扩充到内置存储的分区ID，根据自己的实际情况判断. 如图上是 b364d821-f0b7-4f6f-8c67-eeb62f364ae1
   
   ![](D:\BX02\Desktop\10.png)
   
   
   

5) pm list packages 得到安装的APK的包的名称.
   ![](D:\BX02\Desktop\10.png)

6) pm move-package com.neulion.firetv.ufc.android.amazon b364d821-f0b7-4f6f-8c67-eeb62f364ae1
   根据自己的情况修改，红色部份为要转移的软件包名称（上面第5步得到），蓝色部份为要目标分区ID（上面第4步得到）。

7) 如何判断软件是否安装在扩展存储空间。
   
   ![](D:\BX02\Desktop\11.png)
   
   
   
