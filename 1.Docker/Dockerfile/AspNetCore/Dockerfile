# 基准镜像
# https://hub.docker.com/_/microsoft-dotnet-core-aspnet/
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1

# 维护者信息
LABEL description="Nginx基准镜像，修正时区和主机同步" by="iwenli" maintainer="iwenli<github.com/iwenli>"

# 设置时区
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone

# 设置工作目录
WORKDIR /app