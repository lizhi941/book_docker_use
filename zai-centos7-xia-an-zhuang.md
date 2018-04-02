#### 1.1.1 在centos7下安装

##### 使用yum安装

第一步：关闭防火墙selinux

查看selinux状态

第二步：用yum安装docker

* 设置yum的docker仓库源（docker仓库稳定版stable，开发版edge）

参考Docker官方文档：https://docs.docker.com/install/linux/docker-ce/centos/\#install-docker-ce

```bash
yum-config-manager \
--add-repo \
https://download.docker.com/linux/centos/docker-ce.repo
```

！如果提示没有安装yum-config-manager，这是因为yum默认没有安装自身的管理工具，先运行下面命令安装：

```
yum -y install yum-utils
```

#### 1.1.2 在ubuntu



