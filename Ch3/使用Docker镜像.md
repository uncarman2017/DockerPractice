## Docker基本操作指令

### 1. docker pull
> docker pull willdurand/elk:latest <br/>
> 说明: 获取镜像

### 2. docker images / docker images ls 
> 说明: 查看本机镜像 <br/>
> 选项:
> * -a=true|false: 列出所有镜像文件,默认为否
> * -digests=true|false: 列出镜像的数字摘要值
> * -f=[]: 过滤列出的镜像
> * --format="TEMPLATE": 控制输出格式
> * --no-trunc=true|false: 对输出结果中太长的内容是否进行截断，默认为true
> * -q=true|false: 仅输出ID信息,默认为false


### 3. docker tag 
> docker tag willdurand/elk:latest myelk:latest <br/>
> 说明：给镜像添加标签


### 4. docker inspect
> docker inspect docker.io/willdurand/elk:latest <br/>
> 说明：获取镜像的详细信息

> docker inspect -f {{".Author"}} docker.io/willdurand/elk:latest <br/>
> 说明：获取镜像详细信息中的某个字段

### 5. docker history
> docker history docker.io/willdurand/elk:latest
说明：查看镜像历史

### 6. docker search
> docker search --filter=is-official=true nginx
说明: 搜索关键字为nginx的官方镜像

> docker search --filter=stars=4 tensorflow 
说明：搜索收藏数超过4的官方镜像 <br/>
> 选项:
> * -f: 过滤输出内容
> * --format string: 格式化输出内容
> * --limit int: 限制输出结果个数
> * --no-trunc: 不截断输出结果

### 7. docker rmi / docker image rm
> docker rmi myelk:latest <br/>
> docker [image] rm 017827aa1533  <br/>
说明: 删除镜像<br/>
> 选项:
> * -f: 强制删除镜像，即使有容器依赖它
> * -no-prune: 不要清理未带标签的父镜像

### 8. docker image prune
说明： 清理临时镜像文件
> 选项:
> * -a: 删除所有无用镜像
> * -filter filter: 只清理符合给定过滤器的镜像
> * -f: 强制删除镜像，不提示

### 8. docker run
> docker run docker.io/jupyter/all-spark-notebook:latest
说明: 运行镜像

### 9. docker ps -a
说明: 查看本机所有容器

## 创建镜像的方法

### 1. 基于已有容器创建
docker commit -m "Max Yu's hello world" -a "helloworld clone" **b12477af9471** uncarman/helloworld
 
### 2. 基于本地模板导入
docker import [Docker Repositary And Tag]
说明：[Docker Tag]这个参数输入镜像仓库名和标签 

### 3. 基于Dockerfile创建
docker build -t python:3

## 保存和载入镜像指令
docker save -o [文件路径] [Docker Repositary And Tag] <br/>
说明: 导出镜像至指定文件路径下
例子: docker save -o /usr/local/willdurand_elk_latest.tar docker.io/willdurand/elk:latest

docker load -i [文件路径] 
说明: 导入指定文件路径下的镜像

## 上传镜像
docker push [Docker Repositary And Tag] <br/>
说明：上传镜像文件到DockerHub

## 帮助
docker --help
