# linux基本入门

## 1、目录操作

- 创建目录

  使用 mkdir 命令创建目录

  ```
  mkdir ~/testFolder
  ```


- 切换目录

  使用 cd 命令切换目录

  ```
  cd ~/testFolder/
  ```

  使用 cd ../ 命令切换到上一级目录

  ```
  cd ../
  ```


- 移动目录

  使用 mv 命令移动目录

  ```
  mv ~/testFolder /var/temp/
  ```


- 删除目录

  使用 rm -rf 命令删除目录

  ```
  rm -rf /var/tmp/testFolder/
  ```


- 查看目录下的文件

  使用 ls 命令查看 /etc目录下所有文件和文件夹

  ```
  ls /etc/
  ```

## 2、文件操作

- 创建文件

  使用 touch 命令创建文件

  ```
  touch ~/testFile
  ```

  执行 `ls` 命令, 可以看到刚才新建的 testFile 文件

  ```
  ls ~
  ```

- 复制文件

  使用 cp 命令复制文件

  ```
  cp ~/testFile ~/testNewFile
  ```

- 删除文件

  使用 rm 命令删除文件, 输入 `y` 后回车确认删除

  ```
  rm ~/testFile
  ```

- 查看文件内容

  使用 cat 命令查看 .bash_history 文件内容

  ```
  cat ~/.bash_history
  ```

## 3、过滤, 管道与重定向

- 过滤

  过滤出 /etc/passwd 文件中包含 root 的记录

```
grep 'root' /etc/passwd
```

​     递归地过滤出 /var/log/ 目录中包含 `linux` 的记录

```
grep -r 'linux' /var/log/
```

- 管道

  简单来说, Linux 中管道的作用是将上一个命令的输出作为下一个命令的输入, 像 pipe 一样将各个命令串联起来执行, 管道的操作符是 |

  比如, 我们可以将 cat 和 grep 两个命令用管道组合在一起

  ```
  cat /etc/passwd | grep 'root' 在查看的结果中找出包含'root'的字符
  ```

  过滤出 /etc 目录中名字包含 `ssh` 的目录(不包括子目录)

  ```
  ls /etc | grep 'ssh'
  ```

- 重定向

  可以使用 > 或 < 将命令的输出重定向到一个文件中（覆盖的形式）

  ```
  echo 'Hello World' > ~/test.txt 在test.txt文件中写入'Hello World'
  ```

## 4、运维常用命令

- ping 命令

  对 cloud.tencent.com 发送 4 个 ping 包, 检查与其是否联通

  ```
  ping -c 4 cloud.tencent.com
  ```

- netstat 命令

  netstat 命令用于显示各种网络相关信息，如网络连接, 路由表, 接口状态等等

  列出所有处于监听状态的tcp端口

  ```
  netstat -lt
  ```

  查看所有的端口信息, 包括 PID 和进程名称

  ```
  netstat -tulpn
  ```

- ps 命令

  过滤得到当前系统中的 ssh 进程信息

  ```
  ps -aux | grep 'ssh'
  ```

## 5、其他命令

```
clear 清屏命令
```

```
dir 支持windows下的dir命令
```

```
whoami 查看当前用户是谁
```

```
ls -al 查看隐藏的文件
```

```
echo 'hello world' >> aa.txt 输入一句话到aa.txt文件中去（追加的形式）
```

```
echo 'hello world' > aa.txt 输入一句话到aa.txt文件中去（覆盖的形式）
```

```
man ls | more 一屏幕一屏幕的显示ls的帮助信息，按d表示下一屏幕
```

```
man ls | head -10 显示ls帮助信息的开头10行
```

```
man ls | tail -10 显示ls帮助信息的最后10行
```

```
nano aa.txt 打开文件aa.txt(ubuntu下才有的命令)
```

```
hostname 查看主机名称
```

```
reboot 重启
```

```
find ~ 查询当前目录下的所有文件
```

```
find ~/aa.txt | grep he 查询当前目录下的aa.txt里面的he
```

```
uname -a 查看操作系统的详细信息
```

```
file aa.txt 查看该文件的信息
```

```
tar --zxvf aa.tar.gz 解压文件
```

```
gzip aa.txt和gunzip aa.txt.gz 压缩与解压缩
```

```
mount和unmount 挂载命令与卸载命令
```

```
ps -Af 查看所有进程的信息 或者 ps -Af | more
```

```
ls --help 查看ls的详细信息
```

```
/bin 存放可执行文件
/sbin 存放可执行文件
/boot 引导
/etc 配置目录
/mnt 挂载目录
/home 主目录
/dev 设备目录
/lib 动态库文件
/lib64 64位的动态库文件
/lost+found 存放碎片文件
/proc 存放进程信息
/usr unix system resource，存放系统自带的软件包
```

```
文件类型：
d:目录
-:普通文件
c:字符文件
l:符号链接文件
b:块文件
```

```shell
权限：
文件拥有者 user（用u表示） rwx 可读可写可执行
文件拥有者所在组 group（用g表示） rwx 可读可写可执行
其他的身份 other（用o表示） rwx 可读可写可执行
ugo--->>等价于a
111 111 111（777）表示文件拥有者、文件拥有者所在组和其他的身份对该文件都有可读可写的权限
chmod u+x aa.txt 对aa.txt这个文件的文件拥有者添加可执行的操作

```

