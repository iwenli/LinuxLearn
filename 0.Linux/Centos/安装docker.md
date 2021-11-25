# 安装docker
> 参考：http://www.cnblogs.com/stulzq/p/7743073.html

## 阿里云安装docker
>  https://help.aliyun.com/document_detail/187598.html?spm=5176.22414175.sslink.1.26d4f0deM6HhGA


## 卸载旧版本
---
Docker的旧版本被称为`docker`或`docker-engine`。 如果安装了这些，请卸载它们以及关联的依赖关系。
``` shell
sudo yum remove docker \
docker-client \
docker-client-latest \
docker-common \
docker-latest \
docker-latest-logrotate \
docker-logrotate \
docker-selinux \
docker-engine-selinux \
docker-engine
```

## 安装Docker CE（CE代表社区版）
---
您可以根据需要以不同的方式安装Docker CE：
+ 大多数用户设置了Docker的存储库并从中安装，以方便安装和升级任务。 这是推荐的方法。
+ 某些用户下载RPM软件包并手动安装并手动管理升级。 这在诸如在没有访问互联网的空隙系统上安装Docker的情况下是有用的。
+ 在测试和开发环境中，一些用户选择使用自动化便利脚本来安装Docker。


## 使用存储库进行安装
---
在新的主机上首次安装`Docker CE`之前，需要设置`Docker`存储库。 此后，您可以从存储库安装和更新`Docker`。

1.  安装存储库

    安装必须的包。yum-utils提供了yum-config-manager实用程序，并且device-mapper-persistent-data和lvm2需要devicemapper存储驱动程序。
    ````
    sudo yum install -y yum-utils device-mapper-persistent-data lvm2
    ```
2.  设置稳定存储库
    ```
    sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    ```
3.  可选：启用test和edge。
    ```
    sudo yum-config-manager --enable docker-ce-edge
    sudo yum-config-manager --enable docker-ce-
    #禁用
    sudo yum-config-manager --disable docker-ce-edge
    ```

4.  安装 DOCKER CE
    ```
    sudo yum install docker-ce
    ```

5.  使用 DockerHub 加速器
    https://cloud.tencent.com/document/product/457/9113
    

6.  添加守护进程
    ```
    systemctl enable docker
    ```
