# 1. 查看当前内核版本
```[root@localhost ~]# more /etc/issue```

```CentOS release 6.5 (Final)```

```Kernel \r on an \m```

```[root@localhost ~]# uname -a```

```Linux localhost.localdomain 2.6.32-431.el6.x86_64 #1 SMP Fri Nov 22 03:15:09 UTC 2013 x86_64 x86_64 x86_64 GNU/Linux```

#2. 导入public key
```[root@localhost ~]# rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org
```
#3. 安装ELRepo到CentOS
可以去http://elrepo.org/tiki/tiki-index.php 选择要安装的ELRepo 
```rpm -Uvh http://www.elrepo.org/elrepo-release-6-8.el6.elrepo.noarch.rpm (external link)```
#4. 安装 kernel-lt（lt=long-term）
```[root@localhost ~]# yum --enablerepo=elrepo-kernel install kernel-lt -y```
#5. 编辑grub.conf文件，修改Grub引导顺序
```[root@localhost ~]# vim /etc/grub.conf```
![](http://img.blog.csdn.net/20170428131449682?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvamVmZmxlbw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
因为一般新安装的内核在第一个位置，所以设置default=0，表示启动新内核
#6. 重启
```[root@localhost ~]# reboot```