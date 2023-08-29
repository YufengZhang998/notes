<!--
 * @Description : 
 * @Author      : Yufeng Zhang
 * @Date: 2023-08-29 11:14:47
 * @LastEditTime: 2023-08-29 11:51:44
-->
# 查找内容
```
find 路径 -文件类型/名称 筛选输出（| xargs grep -大小写/行号 --颜色 查找内容）
find ./ -type f | xargs grep -in --color disconnect_current_network
find ./ -iname "*wifi*"  | xargs grep -in --color disconnect_current_network
```

# 查看动态库需要哪些依赖
```
objdump -x ljson-c.so | grep -i need
```

# 查找当前系统支持第三方库
```
apt search libxxx
libxxx-dev：开发包，包含头文件，库文件
```

# 查看软件包信息
```
dpkg -l | grep curl
```

# 查看软件包包含内容
```
搜索软件包：dpkg -l | grep -i libxxx
查看包含内容：dpkg -L libxxx
```

# 设备读写测试：
```
清空caches：echo 3 > /proc/sys/vm/drop_caches
读：time dd if=/tmp/mass_storage/sdb1/test1G of=/dev/null bs=1048576 count=512
写：time dd if=/dev/zero of=/tmp/mass_storage/sdb1/test1G bs=1048576 count=512
```

# 查看端口使用情况
```
netstat -a
```

# 查看系统启动日志
```
dmesg
```

# 回收系统内存
```
sync && echo 3 > /proc/sys/vm/drop_caches
```

# 设置环境变量
```
export HOME=/root
```

# 查看程序运行的系统调用（系统接口）
```
strace ./app-server
```

# 递归删除所有依赖此文件的文件(谨慎操作)
```
sudo apt-get purge --auto-remove python3.10
```

# linux系统进程优先级（优先级最高是-20）
```
查看优先级：ps -o pid,nice,comm,args
设置优先级：renice -n -20 -p [PID]
```
