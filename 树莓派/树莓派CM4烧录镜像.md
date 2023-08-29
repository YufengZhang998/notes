<!--
 * @Description : 
 * @Author      : Yufeng Zhang
 * @Date: 2023-08-29 13:56:51
 * @LastEditTime: 2023-08-29 14:00:48
-->
# 准备工作
1、window安装rpiboote软件
```
https://www.waveshare.net/w/upload/f/f3/Rpiboot_setup.zip
```  
2、Raspberry Pi Imager
```
https://www.raspberrypi.com/software/
```
3、下载树莓派镜像文件
```
https://www.raspberrypi.com/software/operating-systems/
```

# 硬件连接
1、将J2（disable eMMC Boot）位置短接   
2、将usb slave和电脑连接，并断开除usb slave外的所有外设连接（包括电源）   

# 烧录启动工具：
1、以管理员权限运行rpiboot.exe   
2、树莓派上电，电脑设备管理器中会识别出一个BCMxxx设备   
3、rpiboot.exe终端打印烧录启动工具的信息，烧录完成自动关闭终端

# 烧录镜像：
1、启动工具烧录完成，window电脑可以检测到一个USB设备   
2、使用Raspberry Pi Imager烧录镜像   
3、烧录完成，断开（disable eMMC Boot）位置短接，断开usb slave和电脑连接   
4、连接网线，重启树莓派

# 如果启动后USB无法使用：
在boot/config.txt的最后面添加（dtoverlay=dwc2,dr_mode=host）重启即可