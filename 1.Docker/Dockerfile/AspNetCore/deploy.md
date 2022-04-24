# 部署 aspnetcore docker

#### 使用通用镜像部署
``` shell
docker run \
--restart=always \
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
--restart=always \
--name blog.email  \
-dit \
-p 2040:80 \
-v /usr/site/docker/wenlis/blog.email/site/:/app \
registry.cn-beijing.aliyuncs.com/net5/aspnetcore:3.1 \
dotnet 'Moonglade.Notification.API.dll'
```

##### blog
``` shell
docker run \
--restart=always \
--name blog  \
-dit \
-p 2041:80 \
-v /usr/site/docker/wenlis/blog/site/:/app \
-v /usr/site/docker/wenlis/blog/tmp/:/tmp/moonglade \
registry.cn-beijing.aliyuncs.com/net5/aspnetcore:3.1 \
dotnet 'Moonglade.Web.dll'
```


##### passport
``` shell
docker run \
--restart=always \
--name passport  \
-itd \
-p 2051:443 \
-v /usr/site/docker/wenlis/passport/site/:/app \
registry.cn-beijing.aliyuncs.com/net5/aspnetcore:3.1 \
dotnet 'Iwenli.IdentityServer4.STS.Identity.dll'
```


##### ids
``` shell
docker run \
--restart=always \
--name ids  \
-itd \
-p 2050:80 \
-v /usr/site/docker/wenlis/ids/site/:/app \
registry.cn-beijing.aliyuncs.com/net5/aspnetcore:3.1 \
dotnet 'Iwenli.IdentityServer4.Admin.dll'
```

##### api
``` shell
docker run \
--restart=always \
--name api  \
-itd \
-p 1060:80 \
-v /usr/site/docker/api/site/:/app \
registry.cn-beijing.aliyuncs.com/net5/aspnetcore:5.0 \
dotnet 'Coldairarrow.Api.dll'
```


##### api
``` shell
docker run \
--restart=always \
--name wenlis-check  \
-itd \
-p 1051:80 \
-v /usr/site/docker/wenlis/check/site/:/app \
registry.cn-beijing.aliyuncs.com/net5/aspnetcore:5.0.7 \
dotnet 'Dotnet5Check.API.dll'
```
