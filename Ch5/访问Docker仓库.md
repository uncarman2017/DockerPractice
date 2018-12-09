## 5.3 搭建本地私有仓库
docker pull registry:2.6.2 <br/>
docker run -d -p 5000:5000 -v /home/data/registry:/var/lib/registry registry:2.6.2
> 其中路径"/var/lib/registry"为容器内的路径,"/home/data/registry"为本地路径
> 修改docker配置文件: vim /etc/docker/daemon.json
  {
    "insecure-registries":["172.16.100.110:5000"]
  }
 
> 国内镜像加速器配置
> 修改docker配置文件: vim /etc/docker/daemon.json
  {
    "registry-mirrors":["https://1234abcd.mirror.aliyuncs.com"]
  }


