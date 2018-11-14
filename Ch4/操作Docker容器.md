## 创建容器

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

## 停止容器

### 5. docker pause
docker pause [容器ID]
> 说明: 暂停容器执行 <br/>

### 6. docker stop 
docker stop [容器ID]
> 说明: 停止容器执行 <br/>

## 7. docker container prune
> 说明: 自动清除所有处于停止状态的容器 <br/>
 

## 进入容器

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
> * -e: 指定环境变量列表
> * -i=true|false: 打开标准输入接受用户输入命令, 默认为false
> * --privileged=true|false: 是否给执行命令以高权限,默认值为false
> * -t: 分配伪终端，默认值为false
> * -u: 执行命令的用户名或ID 
