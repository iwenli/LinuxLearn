# 部署 jenkins

``` shell 
# pull images
sudo docker pull registry.cn-beijing.aliyuncs.com/net5/jenkins:3.1

# run container
docker run \
--name jenkins01  \
-dit \
--rm \
-p 5080:8080 \
-p 50000:50000 \
registry.cn-beijing.aliyuncs.com/net5/jenkins:3.1
```