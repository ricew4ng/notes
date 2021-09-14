## IOPS是什么?
- 我们知道，常见的web服务，当开发者在回想什么地方可能最耗时的时候，一个点就在数据库查询，换言之，磁盘的IO，那么现在（2021）的磁盘已经发展到什么地步了呢，一块磁盘如果能承受每秒100次IO，也就意味着一次数据库查询（2～4次IO）的耗时在0.02～0.04秒之间。
-
- IOPS：Input/Output Per Second，即每秒的读写次数，是衡量磁盘性能的主要指标之一。
- 磁盘的IOPS，即一秒内磁盘进行多少次I/O读写。
- 磁盘的吞吐量，即每秒磁盘I/O的流量，即磁盘写入加读出的数据的大小。
## IOPS与吞吐量的关系：
	- 每秒I/O吞吐量 = IOPS*平均I/O Size。即I/O Size越大，IOPS越高，那么每秒I/O的吞吐量就越高。因此，我们会认为IOPS和吞吐量的数值越高越好。实际上，对于一个磁盘而言，这两个参数均有其最大值，而且这两个参数也存在着一定的关系。
- IOPS可以继续细分为如下指标：
	- Total IOPS：混合读写和顺序随机I/O负载情况下的磁盘IOPS，这个与实际情况最为相符，大多数应用关注此指标。
	- Random Read IOPS：100%随机读负载情况下的IOPS
	- Random Write IOPS：100%随机写负载情况下的IOPS
	- Sequential Read IOPS：100%顺序读负载情况下的IOPS
	- Sequential Write IOPS：100%顺序写负载情况下的IOPS
- IOPS的benchmark工具有：lometer、loZone、FIO 等。
## IOPS计算公式
-
-
-
## 动手试试
- 西部数据 磁盘的IOPS计算
- 网上找了张它的寻道时间大概 Tseek = 13ms
- ![](https://ser4wang.oss-cn-beijing.aliyuncs.com/20210808230512.png)
- 尝试计算下一块西数3TB磁盘的IOPS：
-
  1. 磁盘寻道时间(图1)，即 Tseek = 13 ms
-
  2. 旋转延时（图2，官方参数 5400 R/min）, 即 Trotation = 60*1000 /5400/2 = 5.55ms
- IOPS = 1000 / ( 13+5.55) = 53.91，也就是一次数据库查询(2~4次IO)最快也要耗时 40 ～ 80ms
-
-