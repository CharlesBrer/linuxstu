# 这是学习linux系统的git库，将我遇到的问题都放到这个仓库中，解决办法写到此文件中

## 1.xshell连接kali的办法
打开kali的终端 输入:leafpad /etc/ssh/sshd_config 打开配置文件

 找到#PermitRootLogin prohibit-password
 将后面的(prohibit-password )改成yes去掉#
 #passwordAuthentication 去掉#号

 然后保存关闭
 打开终端输入:service ssh start开启服务
 然后再输入:service ssh status 确认开启状态

## 2.vmware一些心得
### 1.vm的网卡
   vmnet0和vmnet8为默认的桥接模式和NAT模式的虚拟卡，其余虚拟卡不可以进行这两种模式连接。在NAT网络的创建中，左下角的NAT的网段192.168.XXX.0为此网卡的网段，真实机一般为192.168.XXX.1 虚拟机可自己定义例如192.168.XXX.128

### 2.centos连接xshell
   centos连接网络前，虚拟机保证使用了NAT模式连接
   在终端中使用ifconfig查看当前的ip信息
   在xshell中新建会话，添加主机名称为其ip地址，随后正常操作即可
### 3.centos安装开发工具
```
yum groupinstall -y "Development Tools"
```
