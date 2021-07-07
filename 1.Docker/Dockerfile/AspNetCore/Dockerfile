# 基准镜像
# https://hub.docker.com/_/microsoft-dotnet-core-aspnet/
FROM mcr.microsoft.com/dotnet/aspnet:5.0

# 维护者信息
LABEL description="AspNetCore公共运行容器，通过挂载app目录和entrypoirt来启动基于此环境的项目" by="iwenli" maintainer="iwenli<github.com/iwenli>"

# #定义签名密码
# ENV CertPassword 123456
 
# RUN openssl genrsa -des3 -passout pass:${CertPassword} -out server.key 2048
# RUN openssl rsa -passin pass:${CertPassword} -in server.key -out server.key
# RUN openssl req -sha256 -new -key server.key -out server.csr -subj '/CN=localhost'
# RUN openssl x509 -req -sha256 -days 365 -in server.csr -signkey server.key -out server.crt
# RUN openssl pkcs12 -export -out server.pfx -inkey server.key -in server.crt -certfile server.crt -passout pass:${CertPassword}

# 设置时区
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone

# 安装System.Drawing本机依赖项
# https://github.com/dotnet/dotnet-docker/issues/618
# 安装中文字体  用于验证码  [文泉驿正黑]
RUN apt-get update \
    && apt-get install -y --allow-unauthenticated \
        libc6-dev \
        libgdiplus \
        libx11-dev \
        fontconfig \
        fonts-wqy-zenhei \
     && rm -rf /var/lib/apt/lists/*

ENV ASPNETCORE_URLS=http://+:80 \
    # Enable detection of running in a container
    DOTNET_RUNNING_IN_CONTAINER=true
    
# 设置工作目录
WORKDIR /app