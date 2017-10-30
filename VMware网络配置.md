## 虚拟机网络配置

1、进入虚拟机网络适配器选项

- 桥接方法：虚拟机利用真实网卡与真实机进行网络通信，配置简单，需要设置虚拟机的IP地址与真实机位于同一个网段，占用该此外虚拟机还可与处于同一个网段的其他计算机进行网络通信。
- NAT模式：虚拟机通过VMware8这个虚拟网卡来与真实机通信，不用占用真实网段中的一个网段，可以和本机通信，如果本机可以访问互联网，则虚拟机也可以访问互联网。
- 仅主机模式：虚拟机通过VMware1这个虚拟网卡来与真实机通信，只能和本机通信。

2、centos7下临时分配IP地址（lo表示本地网卡）

- 使用命令：ifconfig

3、配置core-site.xml文件（core-default.html、hdfs-default.html）

- node1为namenode

4、配置hdfs-site.xml文件（hdfs-default.html）

- node2为datanode
- node3为datanode

5、配置slaves文件

6、配置slaves

- 配置secondnode
- 修改主机名（hostnamectl set-hostname <主机名>）
- 免密码登陆：在任何一台节点都可以启动其他的进程

7、做免密码登陆

- node1登陆到node2和node3