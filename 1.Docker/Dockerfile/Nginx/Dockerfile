# 基准镜像
# https://hub.docker.com/_/nginx
FROM nginx:1.16.1

# 维护者信息
LABEL description="Nginx基准镜像，修正时区和主机同步" by="iwenli" maintainer="iwenli<github.com/iwenli>"

# 设置时区
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone
