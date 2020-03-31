# 部署 aspnetcore docker
 
``` shell
# app1 指定端口5000 和 阿里云镜像 启动容器并进入容器（停止后删除）
docker run --name app1 -p 5000:80 \
-it --rm \ 
registry.cn-beijing.aliyuncs.com/iwenli/aspnetcoredemo

# 映射卷到dll目录
docker run --name app -d -p 5000:80 -v /usr/site/docker/app:/app registry.cn-beijing.aliyuncs.com/iwenli/aspnetcoredemo

# 使用通用镜像部署
docker run --name app2 -dit --rm -p 5002:80 -v /usr/site/docker/app:/app registry.cn-beijing.aliyuncs.com/net5/aspnetcore3.1 dotnet 'aspnetapp.dll'

# 配置时区

``` 