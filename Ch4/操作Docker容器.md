## 4.1 创建容器

### 1. docker create
docker create -it [docker仓库:标签] 
> 说明: 从镜像创建容器，创建的容器处于停止状态 <br/>
> 选项: 比较多，可参考书籍上的说明。分为以下三类：
> * 与容器运行模式相关的选项
> * 与容器环境和配置相关的选项
> * 与容器资源限制和安全保护相关的选项
> * 其它选项
>> * -l=[]: 以键值对方式指定容器的标签信息
>> * --label-file=[]: 从文件中读取标签信息

### 2. docker start
docker start [docker仓库:标签]
> 说明: 启动一个容器 <br/>

docker restart [docker仓库:标签]
> 说明: 重启一个容器 <br/>


### 3. docker run
docker run -it [docker仓库:标签] /bin/bash
> 说明: 新建并启动一个容器,创建一个伪终端执行指令 <br/>

docker run -d [docker仓库:标签]
> 说明: 在后台新建并启动一个容器 <br/>

docker container wait [docker仓库:标签]
> 说明：等待容器退出，并打印退出返回结果 <br/>

 
### 4. docker logs
docker logs [容器ID]
> 说明: 获取容器的输出信息 <br/>

## 4.2 停止容器

### 5. docker pause
docker pause [容器ID]
> 说明: 暂停容器执行 <br/>

### 6. docker stop 
docker stop [容器ID]
> 说明: 停止容器执行 <br/>

## 7. docker container prune
> 说明: 自动清除所有处于停止状态的容器 <br/>
 

## 4.3 进入容器

### 8. docker attach 
docker attach [容器ID]
> 说明: 进入容器 <br/>
> 选项:
> * --detach-keys[=[]]: 指定退出attach模式的快捷键序列,默认是CTRL-p, CTRL-q;
> * --no-stdin=true|false: 是否关闭标准输入,默认是保持打开
> * --sig-proxy=true|false: 是否代理收到的系统信号给应用进程, 默认为true

### 9. docker exec
docker exec [容器ID] [shell指令]
> 说明: 在运行中的容器内直接执行任意命令 <br/>
> 选项:
> * -d: 在容器中后台执行指令;
> * --detach-keys="": 指定将容器切回后台的按键
> * -e=[]: 指定环境变量列表
> * -i=true|false: 打开标准输入接受用户输入命令, 默认为false
> * --privileged=true|false: 是否给执行命令以高权限,默认值为false
> * -t=true|false: 分配伪终端，默认值为false
> * -u="": 执行命令的用户名或ID 

## 4.4 删除容器
docker container rm [容器ID]
> 说明: 删除处于终止或退出状态的容器 <br/>
> 选项:
> * -f=false: 是否强行终止并删除一个运行中的容器;
> * -l=false: 删除容器的连接,但保留容器;
> * -v=false: 删除容器挂载的数据卷;

## 4.5 导入和导出容器
### 1. docker container export
docker container export -o="[文件路径]" [容器ID]
> 说明: 导出容器到一个文件(*.tar) <br/>


### 2. docker container import / load
docker container import [ddocker镜像备份文件路径(*.tar)] - [docker仓库:标签]
docker container import /usr/local/docker/test_for_run.tar - test/ubuntu:v1.0
> 说明: 导入容器快照成新的镜像 <br/>
> 选项:
-c=[] : 在导入的同时执行对容器进行修改的Dockerfile指令
-m=[] : 

docker load [docker镜像备份文件路径(*.tar)]
> 说明: 容器快照文件将丢弃所有的历史记录和元数据信息,而镜像存储文件将保存完整记录 <br/>

## 4.6 查看容器
### docker container inspect [容器ID]
> 说明: 查看容器详情

## docker container top [容器ID]
> 说明: 查看容器内进程

## docker container stats [容器ID]
> 说明: 显示CPU,内存，存储，网络使用情况的统计信息
> 选项:
-a : 输出所有容器的统计信息，默认仅在运行中;
-format string: 格式化输出信息
-no-stream: 不持续输出，默认会自动更新持续实时结果;
-no-trunc: 不截断输出信息。

## 4.7 其他容器命令
### docker container cp [容器ID]:[原文件路径] [目标文件路径] 
docker container cp data test:/tmp/
> 说明: 本机和容器之间复制文件

### docker container diff [容器ID]
docker container diff test
> 说明: 查看容器内文件系统的变更

### docker container port
docker container port test
> 说明: 查看容器的端口映射情况

### docker container update
docker update --cpu-quota 1000000 test
> 说明: 更新容器的一些运行时配置，主要是一些资源限制份额




