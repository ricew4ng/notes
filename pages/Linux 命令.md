### top 查看资源占用
	- shift+m：按内存排序
-
### 磁盘相关
	- df -h 查看当前目录下的文件磁盘占比
-
### scp 主机间传输文件
	- 复制本机文件file到目标主机1.1.1.1
		- scp path/to/file user@1.1.1.1:~/
	- 从目标主机1.1.1.1复制文件到本机
		- scp user@1.1.1.1:~/1.1.1.1 ./file
-
- ### 解压缩相关
	- 解压gzip文件
		- tar zxvf x.tar.gz
	- 解压zip文件
		- unzip x.zip
	- 压缩gzip包
-
- ### nc / telnet 相关
	- 在本机开9000端口监听
		- nc -l 9000
	- 连接目标主机9000端口
		- nc -v 1.1.1.1 9000
	- telnet 1.1.1.1 22
-
### aws 命令
	- aws ls s3://bucket_name --endpoint=<endpoint_name>