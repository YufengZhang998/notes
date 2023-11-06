<!--
 * @Description : 
 * @Author      : Yufeng Zhang
 * @Date: 2023-10-30 14:33:10
 * @LastEditTime: 2023-10-31 13:56:29
-->

# linux普通用户使用USB设备

## 创建.rules文件，修改USB设备挂载分组
/etc/udev/rules.d/52-ttyusb.rules
```
# For PL2303
SUBSYSTEM=="tty", ATTRS{idVendor}=="067b", ATTRS{idProduct}=="2303", MODE="0666", GROUP="plugdev"

# For flash tool
SUBSYSTEM=="tty", ATTRS{idVendor}=="0e8d", ATTRS{idProduct}=="2000", MODE="0666", GROUP="plugdev"

# For CP210x
SUBSYSTEM=="tty", ATTRS{idVendor}=="10c4", ATTRS{idProduct}=="ea60", MODE="0666", GROUP="plugdev"

# For CH341
SUBSYSTEM=="tty", ATTRS{idVendor}=="1a86", ATTRS{idProduct}=="7523", MODE="0666", GROUP="plugdev"

# For FT232
SUBSYSTEM=="tty", ATTRS{idVendor}=="0403", ATTRS{idProduct}=="6001", MODE="0666", GROUP="plugdev"
```

## 重启udev服务
sudo service udev restart

## 设备生效
拔插USB设备，触发热拔插事件，新挂载节点生效
