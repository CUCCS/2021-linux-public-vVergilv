# 实验三 Systemd基础

## 实验环境
- Ubuntu 20.04.4 Server 64bit


## 实验流程


**录像1 Systemd命令篇 1~3**

[![asciicast1~3](https://asciinema.org/a/408956.svg)](https://asciinema.org/a/408956)
遇到问题：


**录像2 Systemd命令篇 4-7**

[![asciicast4~7](https://asciinema.org/a/409014.svg)](https://asciinema.org/a/409014)


**录像3 Systemd实战篇 **

[![asciicast](https://asciinema.org/a/409016.svg)](https://asciinema.org/a/409016)

## 自查清单

**如何添加一个用户并使其具备sudo执行程序的权限？**
- 添加新用户：`sudo adduser xx`
- 将其加入sudo权限组`sudo usermod -G sudo -a XX``


**如何将一个用户添加到一个用户组？**

- ```usermod -a -G groupnameD username```


**如何查看当前系统的分区表和文件系统详细信息？**
- `sudo fdisk -l` / `sudo sfdisk -l` / `cfdisk` 分区表信息
- `df `  只会列出已挂载的文件系统信息，但是对于没有挂载的文件系统是查看不到的。
- `lsblk` 分区表和文件系统信息
- cat /proc/partitions——分区表
**如何实现开机自动挂载Virtualbox的共享目录分区？**

在root用户文件 `/etc/rc.local` 中追加如下命令
```
mount -t vboxsf sharing /mnt/share
```
**基于LVM（逻辑分卷管理）的分区如何实现动态扩容和缩减容量？**

```bash
# 动态扩容
lvresize --size -{{SIZE}} --resizefs {{volume_group}}/{{logical_volume}}
# 动态缩减
lvresize --size +{{SIZE}} --resizefs {{volume_group}}/{{logical_volume}}
```
**如何通过systemd设置实现在网络连通时运行一个指定脚本，在网络断开时运行另一个脚本？**

- `locate systemd-networkd.service`找到配置文件
修改 `systemd-networkd.service`配置文件
```
ExecStart=<path_service1> start
ExecStop=<path_service2> stop 
```
之后重新加载并重启`systemd-networkd.service`。

**如何通过systemd设置实现一个脚本在任何情况下被杀死之后会立即重新启动？实现杀不死？**

修改对应的配置文件
```
[Service]
Restart=always
```
之后重新加载并重启

## 遇到的问题

- 修改时区时报错 `Failed to set time: Automatic time synchronization is enabled`

- 需要先关闭时钟同步
  `timedatectl set-ntp no`


## 参考资料
- [Systemd 入门教程：命令篇](http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-commands.html)
- [Systemd 入门教程：实战篇](http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-part-two.html)
- [吕师哥的作业]()
- [修改时间报错](https://blog.csdn.net/xzm5708796/article/details/103733211)