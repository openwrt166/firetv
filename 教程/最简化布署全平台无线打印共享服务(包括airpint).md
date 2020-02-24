#### 优点

1. 布署简单，同时支持airprint，全平台有线，无线打印全部运行。客户端（除Windows外）不用安装驱动，直接找到打印机即可。

2. 实测非常稳定，不用总是重启airprint服务。

#### 前提

Docker 运行环境，USB接口连接打印机

#### 第一步: 在Docker 运行环境下安装CUPS及airprint服务 (如果在群晖下面运行，需要把群晖的网络打印服务关闭)

##### 1)命令行输入:

```
docker run -d --name="airprint" --net="host" --privileged="true" -e TZ="Asia/Shanghai" -e "CUPS_USER_ADMIN"="admin" -e "CUPS_USER_PASSWORD"="admin" -v /volume1/docker/airprint/config:/config -v /dev/bus/usb:/dev/bus/usb yaurora/cups-google-airprint
```

##### 2) 编辑(用vi,vim,nano等)

/volume1/docker/airprint/config/cups/cupsd.conf

按照下面我截的图进行更改

![](D:\BX02\Desktop\cupsd.png)

##### 3)命令行输入:

docker restart airprint

#### 第二步: 在PC浏览器用https://192.168.x.x(你的docker服务ip):663,访问并安装对应打印机驱动。（保持打印机处于连接并打开以搜索到打印机）

服务器已经设置完毕。

1. Windows 平台，用共享名http://192.168.x.x:631/printers/打印机添加打印机并安装本地驱动.

2. Android手机，实现在Android9.0下不用安装任何软件，设置下面“设备连接==》打印”可以直接搜到共享的打印机。如果不行，可以Google Play搜索CUPS Print安装。安装后也不用任何设置不用安装驱动。打印时直接搜到共享的打印机即可。

3. iOS手机，平板，不用安装任何软件，直接Airprint，找到打印机即可打印。
