#### 1.1.1 在centos7下安装

##### 使用yum安装

**第一步：关闭防火墙selinux**

查看selinux状态

**第二步：用yum安装docker**

* 设置yum的docker仓库源（docker仓库稳定版stable，开发版edge）

参考Docker官方文档：[https://docs.docker.com/install/linux/docker-ce/centos/](https://docs.docker.com/install/linux/docker-ce/centos/#install-docker-ce)

```bash
sudo yum-config-manager \
--add-repo \
https://download.docker.com/linux/centos/docker-ce.repo
```

！如果提示没有安装yum-config-manager，这是因为yum默认没有安装自身的管理工具，先运行下面命令安装：

```
sudo yum -y install yum-utils
```

* 安装docker-ce

```
sudo yum install docker-ce #repo默认使用最新的stable仓库
```

！如要安装指定版本：

可以先查看repo中所有的docker版本

```
yum list docker-ce --showduplicates | sort -r
```

选择特定版本

```
sudo yum install <FULLY-QUALIFIED-PACKAGE-NAME> # 例如：sudo yum install docker-ce-17.09.0.ce
```

* 启动并加入开机启动

```
sudo systemctl start docker
sudo systemctl enable docker
```

* docker安装时候默认创建了docker用户组 ，将普通用户加入docker用户组就可以不使用sudo来运动docker命令

```
sudo usermod -aG docker peter #注：添加用户组之后要退出重新登录才会生效，本例普通用户是peter
```

* 运行hello-world镜像来测试是否安装成功。

```
docker run hello-world         #本地没有镜像时会自动从docker hub中下载
```

* **当出现Hello from Docker!即表示安装成功！**

#### 1.1.2 在ubuntu



