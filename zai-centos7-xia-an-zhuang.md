#### 1.1.1 在centos7下安装

##### 使用yum安装

第一步：关闭防火墙selinux

查看selinux状态

第二步：用yum安装docker

* 设置yum的docker仓库源（docker仓库稳定版stable，开发版edge）

参考Docker官方文档：[https://docs.docker.com/v1.13/engine/installation/linux/centos/](https://docs.docker.com/v1.13/engine/installation/linux/centos/ "参考Docker文档说明：Set up the repository")

```bash
yum-config-manager \
--add-repo \
https://docs.docker.com/v1.13/engine/installation/linux/repo_files/centos/docker.repoyum-config-manager \
--add-repo 
```

     ！如果提示该“yum-config-manager”没有安装，这是因为yum没有安装自身的管理工具，运行下面的命令安装:

```bash
yum -y install yum-utils
```



#### 1.1.2 在ubuntu



