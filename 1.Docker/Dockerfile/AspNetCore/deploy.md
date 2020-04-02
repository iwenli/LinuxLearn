# 部署 aspnetcore docker

#### 使用通用镜像部署
``` shell
docker run \
--name app  \
-dit \
--rm \
-p 5000:80 \
-v /usr/site/docker/app:/app \
registry.cn-beijing.aliyuncs.com/net5/aspnetcore:3.1 \
dotnet 'aspnetapp.dll'
```