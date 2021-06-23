# ZLGCAN_python3.7_64
# 环境

 Win10，64位的python3.7
 

# ZLG USBCAN-I驱动
需要下载对应windows驱动才能是的windows下CAN卡别识别。安装好驱动后，CAN卡sys信号灯由红灯变为绿灯，下载地址[USBCAN-I驱动](https://www.zlg.cn/index.php/can/down/down/id/22.html)

# 安装Microsoft Visual C++运行库
由于python通过调用zlgcan.dll等来获取can信息，可能这些dll依赖于C++的dll运行库，所以必须安装。[Microsoft Visual C++运行库](http://manual.zlg.cn/Public/Uploads/2020-06-05/5ed995c271414.zip)


# 下载zlg 64位适配python的例程
需要的dll文件、例程python文件和基于python导出的exe文件在此下载[zlg_python](https://github.com/KinkangLiu/ZLGCAN_python3.7_64)，文件夹如图

![文件夹](https://img-blog.csdnimg.cn/20210623230007254.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNjkwODY0,size_16,color_FFFFFF,t_70)
需要手动将kerneldlls文件夹复制到python.exe根目录，我采用的是anoconda创建的python3.7的虚拟环境，其根目录地址为C:\Users\JQ\ .conda\envs\py37\

# 运行zlgcan.py
用pycharm打开zlgcan.py， 将第443行handle = zcanlib.OpenDevice(ZCAN_USBCAN1, 0,0)中的CAN卡类型更改为你所采用的CAN卡类型，我这里是ZCAN_USBCAN1。然后为pycharm选择你刚复制dll对应的python.exe编译器。然后点击运行即可。
zlgcan_demo.py中实现了GUI界面，直接运行该文件会蹦出界面窗口：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210623231052979.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNjkwODY0,size_16,color_FFFFFF,t_70)
将设备类型选择为你所采用的CAN卡，打开。然后选择CAN卡连接设备所采用的波特率，打开，即可看见报文显示。
zlgcan_demo.exe是由zlgcan_demo.py所生成windows程序，直接双击zlgcan_demo.exe文件即可打开上述界面。
