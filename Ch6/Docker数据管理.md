## 6.1 数据卷 Data Volumes
### docker volume create
docker volume create -d local test

### 其他指令
> * docker volume inspect 
> * docker volume ls
> * docker volume prune
> * docker volume rm
> * docker run --mount
> > -mount选项支持三种了类型的数据卷
- [ ] volume: 普通数据卷, 映射到主机的/var/lib/docker/volumes路径下
- [ ] bind: 绑定数据卷，映射到主机指定路径下
- [ ] tmpfs: 临时数据卷，只存在于内存中
docker run -d -P --name web --mount type=bind, source=/webapp, destination=/opt/webapp training/webapp python app.py 
> 说明: 其中/webapp 是源路径, /opt/webapp是目标路径
> 直接挂载一个文件到容器会异常，推荐的方式是直接挂载文件所在的目录到容器里。

