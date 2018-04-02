制作基础（base image）的主要方法有用tar和用scratch两种方式。这个过程严重依赖于你选用的Linux的发布包。

#### 2.1.1 使用tar制作一个全镜像（full image）

通常，如果想制作某一个linux发行版本的父镜像，就要从运行该版本的机器开始。尽管有一些工具，例如Debian’s

[Debootstrap](https://wiki.debian.org/Debootstrap)，允许你在Debian平台制作Ubuntu镜像。

下面是一个利用工具debootstrap制作Ubuntu父镜像的简单例子：

```
$ sudo debootstrap xenial xenial > /dev/null
$ sudo tar -C xenial -c . | docker import - xenial

a29c15f1bf7a

$ docker run xenial cat /etc/lsb-release

DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=16.04
DISTRIB_CODENAME=xenial
DISTRIB_DESCRIPTION="Ubuntu 16.04 LTS"
```

我们还可以从Docker在github的仓库中找到更多制作父镜像的代码：

* [BusyBox](https://github.com/moby/moby/blob/master/contrib/mkimage/busybox-static)   （BusyBox 是一个集成了三百多个最常用Linux命令和工具的软件）
* CentOS / Scientific Linux CERN \(SLC\) [on Debian/Ubuntu](https://github.com/moby/moby/blob/master/contrib/mkimage/rinse) or [CentOS/RHEL/SLC/etc.](https://github.com/moby/moby/blob/master/contrib/mkimage-yum.sh)

* [Debian / Ubuntu](https://github.com/moby/moby/blob/master/contrib/mkimage/debootstrap)

本节参考了官方文档：[Create a base image](https://docs.docker.com/develop/develop-images/baseimages/)

#### 2.1.2 使用scratch制作一个简单的父镜像（parent images）



