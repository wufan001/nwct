# nwct
内网穿透
# 创建 /opt/nps 目录存放配置文件
mkdir /opt/npc

# 安装wget并且下载配置文件，可根据自己系统将yum替换为apt或其他
yum install -y wget && wget https://img.zeruns.tech/down/conf.zip

# 解压配置文件到 /opt/nps 目录
unzip conf.zip -d /opt/npc

# 拉取 ffdfgdfg/nps 镜像
docker pull ffdfgdfg/npc

# 运行 npc 容器，按提示改好命令，如下图所示
#docker run -d --name=npc --restart=always --net=host ffdfgdfg/npc -server=<ip:port> -vkey=<web界面中显示的密钥> <以及一些其他参数>
#例如
docker run -d --name=npc --restart=always --net=host ffdfgdfg/npc -server=13.124.85.101:2100 -vkey=wufan123456789 -type=tcp
# 查看日志
docker logs npc
# 非docker Linux 安装包方式
# 安装wget并且下载NPC服务端并重命名为 npc.tar.gz ，可根据自己系统将yum替换为apt或其他
yum install -y wget && wget --no-check-certificate -O npc.tar.gz https://img.zeruns.tech/down/linux_amd64_client.tar.gz

# 创建一个名为npc的目录并且解压NPC服务端文件到此目录下，并且进入到npc这个目录下
mkdir /opt/npc && tar -zxvf npc.tar.gz -C /opt/npc && cd /opt/npc

# 安装NPC并启动，按提示改好命令，如下图所示
./npc install -server=<ip:port> -vkey=<web界面中显示的密钥> <以及一些其他参数>
链接：https://url.zeruns.tech/NPS_down
# 启动NPC
sudo npc start
