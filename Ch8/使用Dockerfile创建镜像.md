## 8.1 基本结构
Dockerfile主体内容分为四部分：基础镜像信息、维护者信息、镜像操作指令和容器启动时执行指令

### 指定镜像名称
FROM [镜像名:标签] 
### 指定维护者信息 
LABEL maintainer docker_user<docker_user@email.com>
### 对镜像执行跟随的指令,每执行一条RUN指令，镜像添加新的一层并提交
RUN apt-get update && apt-get install -y nginx
### 指定运行容器时的操作命令
CMD /usr/sbin/nginx



