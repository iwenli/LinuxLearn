# 部署 nginx

> http://www.ruanyifeng.com/blog/2018/02/nginx-docker.html

## 基于官方nginx镜像的配置路径说明
+ 内容文件 `/usr/share/nginx/html`
+ 配置文件 `/etc/nginx/nginx.conf`
+ 日志文件 `/var/log/nginx`

``` shell
# 先运行起来
docker run \
  --name nginx01 \
  -d \
  --rm \
  -p 80:80 \
  registry.cn-beijing.aliyuncs.com/net5/nginx:1.16.1

# 拷贝容器配置
docker container cp nginx01:/etc/nginx /usr/site/nginx
mv nginx conf   

# 删除之前的容器
docker container stop nginx01

# 重新挂载配置运行
docker run \
  --name nginx01 \
  -d \
  --rm \
  -p 80:80 \
  -p 443:443 \
  -v /usr/site/nginx/html/default:/usr/share/nginx/html \
  -v /usr/site/nginx/conf:/usr/share/nginx \
  -v /usr/site/nginx/log:/var/log/nginx \
  registry.cn-beijing.aliyuncs.com/net5/nginx:1.16.1

# 配置证书

```