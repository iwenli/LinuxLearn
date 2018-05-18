# centos7安装加固

1.  更新yum
     ```shell
     yum update
     ```

2.  修改主机名
    ```shell
    hostnamectl set-hostname iwwei 
    ```

3.  添加用户
    ```shell
    useradd cc
    passwd cc 
    ```

4.  修改ssh端口,禁用root
    ```shell
    vim /etc/ssh/sshd_config
    Port 10310   #改ssh端口
    PermitRootLogin no   #禁用root

    systemctl restart sshd.service  #重启ssh
    ```

5.  安装denyhosts
    ```shell
    yum install -y denyhosts
    ```
    > 参考：https://blog.csdn.net/hjd199464/article/details/78315909

6.  安装宝塔
    ```shell
    yum install -y wget && wget -O install.sh http://download.bt.cn/install/install.sh && sh install.sh
    ```
    > 参考：https://www.bt.cn/bbs/thread-1186-1-1.html

7.  