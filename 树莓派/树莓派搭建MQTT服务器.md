<!--
 * @Description : 
 * @Author      : Yufeng Zhang
 * @Date: 2023-08-29 12:07:11
 * @LastEditTime: 2023-08-29 14:08:30
-->
# 安装好python环境、pip工具
## 更换源
```
sudo nano /etc/apt/sources.list
deb http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib rpi
deb-src http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib rpi

sudo nano /etc/apt/sources.list.d/raspi.list
deb http://mirrors.tuna.tsinghua.edu.cn/raspberrypi/ buster main ui
```

## 更新源
```
sudo apt-get update
sudo apt install python3-pip
```

# 下载安装包
网页打开进入选择对应系统版本，https://github.com/emqx/emqx/releases
```
sudo apt-get install lksctp-tools（安装工具）
sudo dpkg -i emqx-edge-raspbian9-v3.1-beta.1_armhf.deb
```

# 启动服务器
```
sudo service emqx start
```