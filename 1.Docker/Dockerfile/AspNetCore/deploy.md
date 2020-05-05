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

##### blog.email
``` shell
docker run \
--name blog.email  \
-dit \
-p 1040:80 \
-v /usr/site/docker/blog.email/site/:/app \
registry.cn-beijing.aliyuncs.com/net5/aspnetcore:3.1 \
dotnet 'Moonglade.Notification.API.dll'
```

##### blog
``` shell
docker run \
--name blog  \
-dit \
-p 1041:80 \
-v /usr/site/docker/blog/site/:/app \
-v /usr/site/docker/blog/tmp/:/tmp/moonglade \
registry.cn-beijing.aliyuncs.com/net5/aspnetcore:3.1 \
dotnet 'Moonglade.Web.dll'
```