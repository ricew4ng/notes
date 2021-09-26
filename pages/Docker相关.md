## 命令
-
  1. 启动容器
	- docker start <container_id>
	- docker run -it --name teamcity-server \
	  -v /data/teamcity/:/data/teamcity_server/datadir \
	  -v /opt/teamcity/log:/opt/teamcity/logs \
	  -p 8111:8111 \
	  jetbrains/teamcity-server
-
-
  2. 进入容器
	- docker exec -it <container_id> /bin/bash
-
-
  3. 进入容器（root权限）
	- docker exec -it -u 0 <container_id> /bin/bash
-
-
  4. 查看所有容器
	- docker ps -a
-
-
  5. 查看所有镜像
	- docker images
-
-
  6. 复制
	- docker cp
-
-
  7. 查看docker日志
	- docker logs [OPTIONS] CONTAINER
	- Options:
		- --details        显示更多的信息
		- -f, --follow         跟踪实时日志
		- --since string   显示自某个timestamp之后的日志，或相对时间，如42m（即42分钟）
		- --tail string    从日志末尾显示多少行日志， 默认是all
		- -t, --timestamps     显示时间戳
		- --until string   显示自某个timestamp之前的日志，或相对时间，如42m（即42分钟）
-
## 编译镜像
- 使用Dockerfile定制镜像： https://yeasy.gitbook.io/docker_practice/image/build
- Docker镜像是分层构成的，当前层之前的层是不能修改的，
- 构建命令
-
  ```bash
  ```
-
## Examples
-
  1. 安装Java镜像
	- docker run -d -it --name teamcity-agent java
	- run 使用镜像创建一个容器
	- -d 容器运行于后台
	- -i 以交互模式运行容器
	- -t 为容器重新分配一个伪输入终端，通常与-i同时使用
-
-
## 可能的问题
-
  1. 加速pull / 切换到国内镜像
	-
	  #+BEGIN_QUOTE
	  curl -sSL https://get.daocloud.io/daotools/set_mirror.sh | sh -s http://d1d9aef0.m.daocloud.io
	  #+END_QUOTE
	- 为了永久性保留更改，您可以修改 /etc/docker/daemon.json 文件并添加上 registry-mirrors 键值。
	  {
	  "registry-mirrors": ["https://registry.docker-cn.com"]
	  }
	- "https://nupozakm.mirror.aliyuncs.com"
-