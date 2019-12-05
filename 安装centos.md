#### 准备
[阿里云镜像](https://developer.aliyun.com/mirror

    下载OS镜像 选择 - > 发行版：centos7  版本7(x86_64-Minimal-1908) 

#### VirtualBox安装虚拟机

     本地新建hxchenc701文件夹，用于将存放待待安装的
     虚拟机
     
     计算机名：hxchenc701（hxchen的centos 7第一台）
     
     类型选择linux，版本Red Hat(64-bit)
     
     分配内存2G, 分配虚拟硬盘固定大小40G
     
     存储中可以看到有控制器:IDE 有控制器:SATA（我们刚分配的虚拟硬盘）

#### 虚拟机安装centos系统
     设置-存储-控制器IDE,分配光驱，选择虚拟光盘文件为刚下载的centos iso文件
     
     启动，选择check,进入欢迎界面，安装过程选择中文简体,设置主机名，设置root密码（弱密码需要点2次完成）,最小安装，开始安装

#### 开启网卡
     输入ip addr验证网卡是否有开启，如果没有则进行下面操作
     cd /etc/sysconfig/network-scripts
     ls -l | grep ifcfg
     vi ifcfg-xxxx （xxxx根据实际情况填写）
     如果ONBOOT=no改为ONBOOT=yes
     reboot
     
#### 安装ifconfig命令

      yum install net-tools
      ifconfig命令测试
      ping www.baidu.com 测试网络是否连通
