### sed命令 操作/编辑文件
	- http://linux.51yip.com/search/sed
	- 常用选项：
	          -n∶使用安静(silent)模式。在一般 sed 的用法中，所有来自 STDIN的资料一般都会被列出到萤幕上。但如果加上 -n 参数后，则只有经过sed 特殊处理的那一行(或者动作)才会被列出来。
	          -e∶直接在指令列模式上进行 sed 的动作编辑；
	          -f∶直接将 sed 的动作写在一个档案内， -f filename 则可以执行 filename 内的sed 动作；
	          -r∶sed 的动作支援的是延伸型正规表示法的语法。(预设是基础正规表示法语法)
	          -i∶直接修改读取的档案内容，而不是由萤幕输出。
	- 常用命令：
	          a   ∶新增， a 的后面可以接字串，而这些字串会在新的一行出现(目前的下一行)～
	          c   ∶取代， c 的后面可以接字串，这些字串可以取代 n1,n2 之间的行！
	          d   ∶删除，因为是删除啊，所以 d 后面通常不接任何咚咚；
	           i   ∶插入， i 的后面可以接字串，而这些字串会在新的一行出现(目前的上一行)；
	           p  ∶列印，亦即将某个选择的资料印出。通常 p 会与参数 sed -n 一起运作～
	           s  ∶取代，可以直接进行取代的工作哩！通常这个 s 的动作可以搭配正规表示法！例如 1,20s/old/new/g
	- sed -n '1p' file  # 展示文件的第一行
	- sed -n '1,2p' file # 展示文件的第一到二行
	- sed -i '1a test add\ncontent1' file # 在第一行后面追加 test add 和 content1 两行文字
-
### awk命令
- awk '{print $1}' file
- cat file | grep -n "xxx" | awk -F ":" '{print $1}' file
-
### 查看资源占用
	- top （linux、mac)
		- shift+m：按内存排序
		- shift+p: 按CPU排序
-
### 磁盘相关
	- df -h 查看磁盘占比
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
		- tar zcvf x.tar.gz ./target_dir
	- 压缩zip包
		- zip -r x.zip ./target_dir
-
- ### nc / telnet 相关
	- 在本机开9000端口监听
		- nc -l 9000
	- 连接目标主机9000端口
		- nc -v 1.1.1.1 9000
	- telnet 1.1.1.1 22
-
## 第三方工具
### AWS CLI
	- aws ls s3://bucket_name --endpoint=<endpoint_name>
	- aws cp target_file s3://bucket/ --endpoint=<endpoint_name>
-
### KVM
	- virsh list --all 列出所有vm ID
	- virsh start vm_id  启动vm
	- virsh destroy vm_id 停止vm
	- virsh create-snapshot-as vm_id snapshow_name
	- virsh snapshot-list vm_id
-
### VMRUN
	-