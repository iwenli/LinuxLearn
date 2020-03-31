# 基准镜像
# https://hub.docker.com/_/microsoft-dotnet-core-aspnet/
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1

# 维护者信息
LABEL description="AspNetCore公共运行容器，通过挂载app目录和entrypoirt来启动基于此环境的项目" by="iwenli" maintainer="iwenli<github.com/iwenli>"

# 设置时区
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone

# 设置工作目录
WORKDIR /app